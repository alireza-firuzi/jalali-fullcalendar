# jalali-fullcalendar

## Quick Install

first of all include css : 

<link rel='stylesheet' href='/assets/dist/js/fullcalendar/fullcalendar.css' />

add a div element width **_fullcalendar_** ID :

<div id='fullcalendar'></div>

after that we need to include javascripts:

<script src='/assets/dist/js/fullcalendar/lib/moment.min.js'></script>
<script src='/assets/dist/js/fullcalendar/persian-date-0.1.8.min.js'></script>
<script src='/assets/dist/js/fullcalendar/fullcalendar.js'></script>
<script src='/assets/dist/js/fullcalendar/lang-all.js'></script>

at the end :

<script type="text/javascript">
 $(document).ready(function () {

        // page is now ready, initialize the calendar...

        $('#fullcalendar').fullCalendar({
            header: {
                left: 'next,prev today',
                center: 'title',
                right: 'month,agendaWeek,agendaDay'
            },
            lang1: 'persianJalali',
            lang: 'fa',
            fistDay: 6,
            isRTL: true,
            eventLimit: true, // for all non-agenda views
            loading: function (bool) {
                if (bool) {
                    $.isLoading({text: "در حال پردازش ..."});
                } else {
                    $.isLoading("hide");
                }
            },
//            editable: true,
            dayClick: function (date, allDay, jsEvent, view) {
//                console.log(date);
            },
            eventClick: function (calEvent, jsEvent, view) {
//                console.log(calEvent);

                $('#eventModal .modal-body').text(calEvent.title);
                $('#eventModal').modal('toggle');
                ;
            },
            eventDrop: function (calEvent, dayDelta, minuteDelta, allDay,
                    revertFunc, jsEvent, ui, view) {
//                console.log(view);
            },
            eventResize: function (calEvent, dayDelta, minuteDelta, revertFunc) {
//                console.log(dayDelta);
            },
            events: '/calendar/events'
        })

    });
</script>

for more information visit [fullcander documentation](http://fullcalendar.io/docs/)
