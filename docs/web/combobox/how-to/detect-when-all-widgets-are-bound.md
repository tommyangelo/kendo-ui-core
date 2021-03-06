---
title: Detect When All Widgets Are Bound
page_title: Detect When All Widgets Are Bound | Kendo UI ComboBox Widget
description: "Learn how to use promises to detect when all widgets are bound in Kendo UI ComboBox."
slug: howto_detect_when_widgets_bound_combobox
position: 7
---

# Detect When All Widgets Are Bound

The example below demonstrates how to use promises to detect when all widgets are bound.

###### Example

```html
  <div id="example">
    <div class="demo-section k-header">
      <h4>View Order Details</h4>
      <p>
        <label for="categories">Categories:</label><input id="categories" style="width: 270px" value="1"/>
      </p>
      <p>
        <label for="products">Products:</label><input id="products" style="width: 270px" />
      </p>
    </div>

    <style scoped>
      .demo-section {
        width: 400px;
      }
      .demo-section p {
        margin-top: 1em;
      }
      .demo-section label {
        display: inline-block;
        width: 100px;
        padding-right: 5px;
        text-align: right;
      }
      .demo-section .k-button {
        margin: 1em 0 0 105px;
      }
      .k-readonly
      {
        color: gray;
      }
    </style>

    <script>
      $(document).ready(function() {
        var promises = [];

        var change = function() {
          this.deferred.resolve();   
        }

        var categories = $("#categories").kendoDropDownList({
          dataTextField: "CategoryName",
          dataValueField: "CategoryID",
          dataSource: {
            type: "odata",
            serverFiltering: true,
            transport: {
              read: "http://demos.kendoui.com/service/Northwind.svc/Categories"
            },
            requestStart: function() {
              this.deferred = $.Deferred();
              promises.push(this.deferred.promise());
            }
          }
        }).data("kendoDropDownList");

        var products = $("#products").kendoDropDownList({
          dataTextField: "ProductName",
          dataValueField: "ProductID",
          dataSource: {
            type: "odata",
            serverFiltering: true,
            transport: {
              read: "http://demos.kendoui.com/service/Northwind.svc/Products"
            },
            requestStart: function() {
              this.deferred = $.Deferred();
              promises.push(this.deferred.promise());
            }
          }
        }).data("kendoDropDownList");

        categories.dataSource.bind("change", change);
        products.dataSource.bind("change", change);

        $.when.apply(null, promises)
        .done(function() {
          console.log("done");
          console.log(categories.value());
          console.log(products.value());
        });
      });
    </script>
  </div>
```

## See Also

Other Kendo UI ComboBox how-to examples:

* [Add Option Label Manually]({% slug howto_add_option_label_manually_combobox %})
* [Initialize ComboBox with Templates]({% slug howto_declaratively_initialize_with_templates_combobox %})
* [Prevent Adding Custom Values]({% slug howto_prevent_adding_custom_values_combobox %})
* [Prevent POST on ENTER Key Press]({% slug howto_prevent_post_onpressing_enter_combobox %})
* [Bypass Boundary Detection]({% slug howto_bypass_boudary_detection_combobox %})
* [Make Visible Input Readonly]({% slug howto_make_visible_inputs_readonly_combobox %})
* [Search for Items by Dragging to Input]({% slug howto_search_items_dragging_toinput_combobox %})
* [Underline Matched Search]({% slug howto_underline_matched_search_combobox %})
* [Clear Filter on Open]({% slug howto_clear_filter_open_combobox %})
* [Open ComboBox When `onfocus` is Triggered]({% slug howto_open_onfocus_combobox %})
* [Configure Deferred Value Binding]({% slug howto_configure_deffered_value_binding_combobox %})
* [Expand Background of Long List Items]({% slug howto_expand_background_longlist_items_combobox %})
* [Expand ComboBox Located in Bootstrap Layout]({% slug howto_expand_widget_bootstrap_widget_combobox %})
* [Implement Cascading with Local Data]({% slug howto_implement_cascading_local_data_combobox %})
* [Select Items on TAB]({% slug howto_select_items_ontab_combobox %})
* [Blur the ComboBox after Select]({% slug howto_blur_after_select_combobox %})
* [Disable Child Cascading ComboBoxes]({% slug howto_disable_child_cascading_combobox %})