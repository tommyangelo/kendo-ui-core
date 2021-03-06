---
title: Restrict User Input to Min/Max Values
page_title: Restrict User Input to Min/Max Values | Kendo UI DatePicker Widget
description: "Learn how to restrict user input by applying minimum and maximum values in the Kendo UI DatePicker widget."
slug: howto_restrict_user_input_minandmax_values_datepicker
position: 9
---

# Restrict User Input to Min/Max Values

The example below demonstrates how to restrict user input to min/max values set via the widget configuration.

#### Example:

```html
    <input id="DOB" value="30/06/2010" />
  	<script>
      $(function() {
        $("#DOB").kendoDatePicker({
          format: "dd/MM/yyyy",
          min: new Date(2000, 10, 10),
          max: new Date(2020, 10, 10),
          change: onDOBChange
        });
      });
    </script>
  
    <script>
        function onDOBChange(e) {
            var dt = e.sender;
          	var value = dt.value();
          	
          	if (value === null) {
              value = kendo.parseDate(dt.element.val(), dt.options.parseFormats);
            }
          
            if (value < dt.min()) {
                dt.value(dt.min());
            }else if (value > dt.max()) {
                dt.value(dt.max());
            }
        }
    </script>
```

## See Also

Other Kendo UI DatePicker how-to examples:

* [Create Date Masking]({% slug howto_create_date_masking_datepicker %})
* [Select Ranges between DatePickers]({% slug howto_select_ranges_between_datepicker %})
* [Set the First Weekday]({% slug howto_set_first_weekday_datepicker %})
* [Integrate DatePicker with DateJS Library]({% slug howto_integrate_withdatejs_library_datepicker %})
* [Disable Dates]({% slug howto_disable_dates_datepicker %})
* [Hide the Deafult Button]({% slug howto_hide_default_button_datepicker %})
* [Globally Modify Default Options]({% slug howto_globally_modify_default_options_datepicker %})
* [Persist Entered Dates]({% slug howto_persist_entered_dates_datepicker %})
* [Make Input Elements Readonly]({% slug howto_make_input_elements_readonly_datepicker %})
* [Resize Calendar Based on Input Width]({% slug howto_use_resize_calendar_basedon_input_width_datepicker %})
* [Use AngularJS Copy Functionality]({% slug howto_use_angularjs_copy_functionality_datepicker %})
* [Show Out-of-Range Dates as Disabled]({% slug howto_show_outofrange_dates_disabled_datepicker %})
* [Submit Forms on ENTER]({% slug howto_submmit_forms_onenter_datepicker %})