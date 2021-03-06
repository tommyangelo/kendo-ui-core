---
title: Grouping
page_title: Grouping | Kendo UI ComboBox Widget
description: "Learn how to configure grouping in Kendo UI ComboBox, DropDownList, AutoComplete and MultiSelect widgets."
slug: grouping_kendoui_combobox_widget
position: 2
---

# Grouping

As of Kendo UI Q1 2015 (2015.1.318) [Kendo UI AutoComplete](http://demos.telerik.com/kendo-ui/autocomplete/index), [ComboBox](http://demos.telerik.com/kendo-ui/combobox/index), [DropDownList](http://demos.telerik.com/kendo-ui/dropdownlist/index) and [MultiSelect](http://demos.telerik.com/kendo-ui/multiselect/index) widgets support binding to a grouped [datasource](http://docs.telerik.com/kendo-ui/framework/datasource/overview). This functionality allows you to display data items categorized by a specific model field. 

For more details about the data source grouping functionality, refer to the [group configuration article](http://docs.telerik.com/kendo-ui/api/javascript/data/datasource#configuration-group).

## Enable

Enable the grouping functionality in a ComboBox by using the remote transport and a grouped data source:

```html
<div class="demo-section k-header">
    <h4>Customers</h4>
    <input id="customers" style="width: 400px" />
</div>

<script>
    $(document).ready(function() {
        $("#customers").kendoComboBox({
            dataTextField: "ContactName",
            dataValueField: "CustomerID",
            height: 200,
            dataSource: {
                type: "odata",
                transport: {
                    read: "http://demos.telerik.com/kendo-ui/service/Northwind.svc/Customers"
                },
                group: { field: "Country" } //group the data by 'Country' field
            }
        });
    });
</script>
```

## Configure

In order to display grouped items in the widget, you will need to group the data source component using its [group configuration](http://docs.telerik.com/kendo-ui/api/javascript/data/datasource#configuration-group). Once the group option is defined, the widget will automatically display the suggestion items grouped.

## Customize

The widget exposes [groupTemplate](http://docs.telerik.com/kendo-ui/api/javascript/ui/combobox#configuration-groupTemplate) and [fixedGroupedTemplate](http://docs.telerik.com/kendo-ui/api/javascript/ui/combobox#configuration-fixedGroupTemplate) templates that allow to configure rendering of the group titles.

### Inline Group Title

To customize the inline group title displayed next to the suggestion item in the popup element, you will need to use the [groupTemplate](http://docs.telerik.com/kendo-ui/api/javascript/ui/combobox#configuration-groupTemplate) option. It is rendered in the absolute positioned, right aligned group element displayed in every first element of each new group.

The parameter passed to the template is the group title value.

###### Example - define a custom group template

```html
<div class="demo-section k-header">
    <h4>Customers</h4>
    <input id="customers" style="width: 400px" />
</div>

<script>
    $(document).ready(function() {
        $("#customers").kendoComboBox({
            height: 200,
            groupTemplate: "<strong>#:data#</strong>", //`data` is the title of the group
            dataTextField: "ContactName",
            dataValueField: "CustomerID",
            dataSource: {
                type: "odata",
                transport: {
                    read: "http://demos.telerik.com/kendo-ui/service/Northwind.svc/Customers"
                },
                group: { field: "Country" } //group the data by 'Country' field
            }
        });
    });
</script>
```

### Fixed Group Header

To customize the group title displayed in the fixed group header positioned on top of the list, you will need to use the [fixedGroupTemplate](http://docs.telerik.com/kendo-ui/api/javascript/ui/combobox#configuration-fixedGroupTemplate) option. It shows the group title of the current visible group. This means that the value is updated dynamically on the scroll position of the grouped list.

The parameter passed to the template is the group title value.

###### Example - define a custom fixed group template

```html
<div class="demo-section k-header">
    <h4>Customers</h4>
    <input id="customers" style="width: 400px" />
</div>

<script>
    $(document).ready(function() {
        $("#customers").kendoComboBox({
            height: 200,
            fixedGroupedTemplate: "<strong>#:data#</strong>", //`data` is the title of the group
            dataTextField: "ContactName",
            dataValueField: "CustomerID",
            dataSource: {
                type: "odata",
                transport: {
                    read: "http://demos.telerik.com/kendo-ui/service/Northwind.svc/Customers"
                },
                group: { field: "Country" } //group the data by 'Country' field
            }
        });
    });
</script>
```

## See Also

Other articles on Kendo UI ComboBox:

* [Overview]({% slug overview_kendoui_combobox_widget %})
* [Virtualization]({% slug virtualization_kendoui_combobox_widget %})
* [Server Filtering]({% slug server_filtering_kendoui_combobox_widget %})
* [Cascading ComboBoxes]({% slug cascading_kendoui_combobox_widget %})
* [Add Option Label Manually]({% slug howto_add_option_label_manually_combobox %})
* [Implement Cascading with Local Data]({% slug howto_implement_cascading_local_data_combobox %})
* [Configure Deferred Value Binding]({% slug howto_configure_deffered_value_binding_combobox %})
* [Declaratively Initialize ComboBox with Templates]({% slug howto_declaratively_initialize_with_templates_combobox %})
* [Clear Filter on Open]({% slug howto_clear_filter_open_combobox %})
* [Detect When All Widgets Are Bound]({% slug howto_detect_when_widgets_bound_combobox %})
* [Bypass Boundary Detection]({% slug howto_bypass_boudary_detection_combobox %})
* [Disable Child Cascading ComboBoxes]({% slug howto_disable_child_cascading_combobox %})
* [Expand Background of Long List Items]({% slug howto_expand_background_longlist_items_combobox %})