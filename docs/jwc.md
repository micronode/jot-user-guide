[JOT API]: jotapi.md

# Jot Web Components
Jot Web Components (JWC) provides a collection of Web Components that can be combined in various ways to implement a complete JOT-based Web user interface. JWC supports data management (i.e. retrieval and persistence) via the [JOT API].

## Overview
Jot Web Components are named according to the supported JOT API endpoints, such that a typical naming convention is as follows:

    jot-<endpoint>-<component_type>

So for example, a calendar list web component would be called:

    jot-calendar-list

## Common Elements
As the implementation of components for different endpoints will share much of the same code, a set of common superclass components are provided. These aim to reduce code duplication and improve consistency across all components.

The common elements are:

* jot-element - base class for all Jot Web Components
* jot-list-element - functionality to support list rendering
* jot-geo-element - functionality to support geolocation rendering
* jot-grid-element - support for rendering information grids
* jot-editor-element - base class for editor components

