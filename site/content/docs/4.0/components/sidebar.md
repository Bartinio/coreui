---
layout: docs
title: Sidebar
description: Bootstrap Sidebar is a powerful and customizable responsive navigation component for any type of vertical navigation. Bootstrap Sidebar come with built-in support for branding, navigation, and more.
group: components
aliases:
  - "/components/sidebar/"
toc: true
---

<style>
.c-content .sidebar {
  position: static !important;
  width: 200px;
  height: 500px;
}
</style>

## How it works

Here's what you need to know before getting started with the sidebar:

- Sidebar requires a wrapping `.sidebar-`.
- Sidebar is hidden by default. Force it to be shown by adding `.sidebar-{-sm|-md|-lg|-xl|-xxl}-show` or `.sidebar-show` to the `.sidebar`.
- Ensure accessibility by using a `<nav>` element or, if using a more generic element such as a `<div>`, add a `role="navigation"` to `.sidebar-nav` to explicitly identify it as a landmark region for users of assistive technologies.

Read on for an example and list of supported sub-components.

## Supported content

Sidebar come with built-in support for a handful of sub-components. Choose from the following as needed:

- `.sidebar-header` for optional header.
- `.sidebar-brand` for your company, product, or project name.
- `.sidebar-nav` for a full-height and lightweight navigation (including support for dropdowns).
- `.sidebar-footer` for optional footer.
- `.sidebar-toggler` for use with our minimizer plugin.

## Example

{{< example >}}
{{< sidebar.inline >}}
<div class="sidebar sidebar-show">
  <ul class="sidebar-nav">
    <li class="nav-title">Nav Title</li>
    <li class="nav-item">
      <a class="nav-link" href="#">
        <i class="nav-icon cil-speedometer"></i> Nav item
      </a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="#">
        <i class="nav-icon cil-speedometer"></i> With badge
        <span class="badge badge-primary">NEW</span>
      </a>
    </li>
    <li class="nav-item nav-group">
      <a class="nav-link nav-group-toggle" href="#">
        <i class="nav-icon cil-puzzle"></i> Nav dropdown
      </a>
      <ul class="nav-group-items">
        <li class="nav-item">
          <a class="nav-link" href="#">
            <i class="nav-icon cil-puzzle"></i> Nav dropdown item
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">
            <i class="nav-icon cil-puzzle"></i> Nav dropdown item
          </a>
        </li>
      </ul>
    </li>
    <li class="nav-item mt-auto">
      <a class="nav-link nav-link-success" href="https://coreui.io">
        <i class="nav-icon cil-cloud-download"></i> Download CoreUI</a>
    </li>
    <li class="nav-item">
      <a class="nav-link nav-link-danger" href="https://coreui.io/pro/">
        <i class="nav-icon cil-layers"></i> Try CoreUI
        <strong>PRO</strong>
      </a>
    </li>
  </ul>
  <button class="sidebar-minimizer c-brand-minimizer" type="button"></button>
</div>
{{< /sidebar.inline >}}
{{< /example >}}

## Responsive behaviors

Sidebar can utilize `.sidebar-{-sm|-md|-lg|-xl|-xxl}-show` classes to change whether is visible or hidden. You can easily choose when to show or hide sidebar.

For sidebar that is always visible, add the `.sidebar-show` class on the sidebar

### Sidebar toggler

Add `data-toggle="sidebar{-sm|-md|-lg|-xl|-xxl}-show"` to `.sidebar-toggler`.

{{< example >}}
{{< sidebar.inline >}}
<header class="navbar navbar-light">
  <button class="navbar-toggler sidebar-toggler" type="button" data-toggle="sidebar-show">
    <span class="navbar-toggler-icon"></span>
  </button>
</header>
{{< /sidebar.inline >}}
{{< /example >}}

## Light sidebar {class="pro-component"}

Opt into darker dropdowns to match a dark navbar or custom style by adding .dropdown-menu-dark onto an existing .dropdown-menu. No changes are required to the dropdown items.

{{< example >}}
{{< sidebar.inline >}}
<div class="bg-light">
<div class="sidebar sidebar-light sidebar-show">
  <ul class="sidebar-nav">
    <li class="nav-title">Nav Title</li>
    <li class="nav-item">
      <a class="nav-link" href="#">
        <i class="nav-icon cil-speedometer"></i> Nav item
      </a>
    </li>
    <li class="nav-item">
      <a class="nav-link" href="#">
        <i class="nav-icon cil-speedometer"></i> With badge
        <span class="badge badge-primary">NEW</span>
      </a>
    </li>
    <li class="nav-item nav-group">
      <a class="nav-link nav-group-toggle" href="#">
        <i class="nav-icon cil-puzzle"></i> Nav dropdown
      </a>
      <ul class="nav-group-items">
        <li class="nav-item">
          <a class="nav-link" href="#">
            <i class="nav-icon cil-puzzle"></i> Nav dropdown item
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">
            <i class="nav-icon cil-puzzle"></i> Nav dropdown item
          </a>
        </li>
      </ul>
    </li>
    <li class="nav-item mt-auto">
      <a class="nav-link nav-link-success" href="https://coreui.io">
        <i class="nav-icon cil-cloud-download"></i> Download CoreUI</a>
    </li>
    <li class="nav-item">
      <a class="nav-link nav-link-danger" href="https://coreui.io/pro/">
        <i class="nav-icon cil-layers"></i> Try CoreUI
        <strong>PRO</strong>
      </a>
    </li>
  </ul>
  <button class="sidebar-minimizer c-brand-minimizer" type="button"></button>
</div>
</div>
{{< /sidebar.inline >}}
{{< /example >}}


## JavaScript behavior

### Methods

You can create a sidebar instance with the sidebar constructor, for example:

{{< highlight js >}}
var mySidebar = document.querySelector('#mySidebar')
var sidebar = new coreui.Sidebar(mySidebar)
{{< /highlight >}}


{{< bs-table "table text-left" >}}
| Method | Description |
| --- | --- |
| `open` | Shows the sidebar. |
| `close` | Hides the sidebar. |
| `toggle` | Toggles the sidebar to opened or closed. |
| `minimize` | Minimizes the sidebar. |
| `getInstance` | Static method which allows you to get the sidebar instance associated with a DOM element. |
{{< /bs-table >}}

{{< highlight js >}}
var sidebarNode = document.querySelector('#mySidebar')
var sidebar = coreui.Sidebar.getInstance(sidebarNode)
sidebar.close()
{{< /highlight >}}

### Events

Bootstrap's alert plugin exposes a few events for hooking into alert functionality.

{{< bs-table "table text-left" >}}
| Event | Description |
| --- | --- |
| `close.coreui.sidebar` | This event is fired immediately when the `close` instance method has been called. |
| `closed.coreui.sidebar` | This event is fired when the sidebar has finished being closed from the user (will wait for CSS transitions to complete). |
| `open.coreui.sidebar` | This event fires immediately when the `open` instance method is called. |
| `opened.coreui.sidebar` | This event is fired when the sidebar has been made visible to the user (will wait for CSS transitions to complete) |
{{< /bs-table >}}

{{< highlight js >}}
var mySidebar = document.getElementById('mySidebar')
mySidebar.addEventListener('closed.coreui.sidebar', function () {
  // do something…
})
{{< /highlight >}}

## Customizing

### SASS
{{< scss-docs name="sidebar-variables" file="scss/_variables.scss" >}}

### CSS Vars
{{< css-vars-docs file="scss/sidebar/_sidebar.scss" >}}
