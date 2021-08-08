[API]: jotapi.md

#  Introduction
JOT is a persistence management framework for scheduling and calendar data, that incorporates not just backend persistence but also presentation layer and API components. In some ways JOT may be seen as a rapid prototyping tool, but it may also be used to build highly resilient, well performing production systems and components.

## The iCalendar Specification
JOT is based on a collection of published specifications known as iCalendar, that define interoperability standards adopted by a broad range of productivity software. In using these specifications as the basis for data modeling and API design, JOT is aiming for a level of interoperability rarely achieved in productivity and scheduling software.

## JOT API
The anchoring component of the JOT framework is the Application Programming Interface ([API]). Whilst this may appear to be an odd choice for an achor, having the data model downstream and presentation layer upstream, the primary reason is that the API can be language-agnostic, and thus support multiple implementations of presentation and data modeling components.
