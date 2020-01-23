# PeopleSoftFullCalendar
PeopleCode wrapper to implement FullCalendar in PeopleSoft. [https://fullcalendar.io](https://fullcalendar.io)

## To Import
Because subsequent version of PEopleTools often don't allow you to import Projects from pervious versions I've copied all code into text files. 

You'll want an Application Package with the folowing structure:

    Package
      |--Event
      |--FullCalendar
      |--SubClasses
           |--DemoCalendar
           |--InstructorSchedule

## Example Component

You need a Component with a Page with an HTML Area on it.

The following Stylesheet and JavaScript needs to be added to your component under Component Properties > Style :

      StyleSheet.RX_FULL_CALENDAR_CSS
      JavaScript.RX_MOMENT_JS
      JavaScript.RX_JQUERY_3_3_1_JS
      JavaScript.RX_FULL_CALENDAR_3_9_0_JS
       
## Example Code

    import YOUR_APP_PACKAGE:CALENDAR:FullCalendar;

    local any &Calendar;
    local any &Event;
    
    &Calendar = create YOUR_APP_PACKAGE:CALENDAR:FullCalendar();
    
    &Event = &Calendar.NewEvent();
    &Event.Title = "Christmas";
    &Event.Start = "2018-12-25T09:00";
    &Event.End = "2018-12-25T17:00";
    &Event.ClassName = "red";
    &Calendar.Events.Push(&Event);
    
    &Event = &Calendar.NewEvent();
    &Event.Title = "Boxing Day";
    &Event.Start = "2018-12-25T09:00";
    &Event.End = "2018-12-25T17:00";
    &Event.ClassName = "orange";
    &Calendar.Events.Push(&Event);

    PS_SOME_RECORD.HTMLAREA.Value = &Calendar.Draw();

You'll have to copy-pasta the CSS and JavaScript into HTML Objects. I *highly* recommend you use *PeopleTools > Portal > Branding > Branding Objects* to do this as it won't corrupt the sometimes minimised files by adding random carriage returns and the like.

Should be nice to extend, there's already an example in the *Subclasses* package.
