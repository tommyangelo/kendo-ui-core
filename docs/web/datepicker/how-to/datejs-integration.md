---
title: Integrate DatePicker with DateJS Library
page_title: Integrate DatePicker with DateJS Library | Kendo UI DatePicker Widget
description: "Learn how to integrate the Kendo UI DatePicker widget with the DateJS library and use its syntactic sugar."
slug: howto_integrate_withdatejs_library_datepicker
position: 5
---

# Integrate DatePicker with DateJS Library

The example below demonstrates how to integrate the Kendo UI DatePicker with DateJS and use its syntactic sugar.

###### Example

```html
    <div id="email-settings">
        <div class="display-picker">
            <input id="datepicker" placeholder="type 'next friday'" style="width:150px;" />
        </div>
        <div class="archive-picker">
            <input id="monthpicker" value="November 2011" style="width:150px" />
        </div>
        <p>Integration with the <a target="_blank" href="http://www.datejs.com/">DateJS</a> library</p>
    </div>
    <script>
        $(document).ready(function() {
            // create DatePicker from input HTML element
            $("#datepicker").kendoDatePicker();

            $("#monthpicker").kendoDatePicker({
                // defines the start view
                start: "year",

                // defines when the calendar should return date
                depth: "year",

                // display month and year in the input
                format: "MMMM yyyy"
            });

            //Parse input value on blur using DateJS
            $("[data-role=datepicker]").on("blur", function() {
                var element = $(this);
                var widget = element.data("kendoDatePicker");

                if (element.val()) {
                  widget.value(Date.parse(element.val()));
                }
            });
        });
    </script>
```

## See Also

Other Kendo UI DatePicker how-to examples:

* [Create Date Masking]({% slug howto_create_date_masking_datepicker %})
* [Select Ranges between DatePickers]({% slug howto_select_ranges_between_datepicker %})
* [Set the First Weekday]({% slug howto_set_first_weekday_datepicker %})
* [Use AngularJS Copy Functionality]({% slug howto_use_angularjs_copy_functionality_datepicker %})
* [Disable Dates]({% slug howto_disable_dates_datepicker %})
* [Hide the Deafult Button]({% slug howto_hide_default_button_datepicker %})
* [Globally Modify Default Options]({% slug howto_globally_modify_default_options_datepicker %})
* [Persist Entered Dates]({% slug howto_persist_entered_dates_datepicker %})
* [Make Input Elements Readonly]({% slug howto_make_input_elements_readonly_datepicker %})
* [Resize Calendar Based on Input Width]({% slug howto_use_resize_calendar_basedon_input_width_datepicker %})
* [Restrict User Input to Min/Max Values]({% slug howto_restrict_user_input_minandmax_values_datepicker %})
* [Show Out-of-Range Dates as Disabled]({% slug howto_show_outofrange_dates_disabled_datepicker %})
* [Submit Forms on ENTER]({% slug howto_submmit_forms_onenter_datepicker %})