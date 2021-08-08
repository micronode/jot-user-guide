# JOT API
The JOT API provides the anchoring specification of the JOT framework.

## Overview
The JOT API actually consists of two independent APIs: one for calendar data, and another for entity data. The calendar API is based on the published iCalendar specification, and supports events, tasks, availability and journaling. The enity API is based on the vCard specification, and supports individuals, organizations, resources and groups.

## JOT Calendar API (jotcal)
The jotcal API supports endpoints for the following resource types:

* `Calendar` - a collection of calendar components (i.e. events, journals, todos, availability)
* `Event` - a calendar component that defines a scheduled, optionally recurring event
* `Journal` - a calendar component used to record observations and notes
* `ToDo` - a calendar component for tasks and workflow items
* `Alarm` - a sub-component of other components to define actions triggered by component properties/state
* `Availability` - a component that defines the availability of individuals and resources
* `Attachment` - a binary endpoint for uploading/accessing component attachments
* `FreeBusy` - a non-persistent component that is constructed from the blocked time of other components

## JOT Entity API (jotcard)
The jotcard API supports endpoints for the following resource types:

* `Group` - an entity that defines a collection of individuals and resources
* `Card` - an entity that defines an individual or resource


