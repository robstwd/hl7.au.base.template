# ig-template-hl7

package id = hl7.au.base.template

Base template for HL7-published IGs.  Foundation for family-specific templates

## Inheritance
This template inherits directly from the HL7 template: `fhir.base.template#current` 

https://github.com/HL7/ig-template-base

## Template inclusions

### 1. ./includes
#### a) `/_append.fragment-css.html`
css styling - css/hl7.css

* footer background colour
* navbar inverse colour
* generic settings common to all HL7 IGs
* note-to-balloters styling

#### b) `/_append.fragment-header.html`
To the header, adds:
* HL7AU Australia logo in header, on the left side `hl7-logo.png`

### 2. ./layouts
#### a) `layout-ext.html`
This is the layout template for all extensions and it is changed from the [upstream version](https://github.com/HL7/ig-template-base/blob/master/layouts/layout-ext.html) in these material ways:
* the heading "Context of Use" is not present (*why would this be needed?*). Other IGs like US Core have retained this option with what I think is a better means of identifying the context of use.
* the heading "Usage info" is not present (*this probably should also be removed in the upstream version*)
* the tab `Text Summary` has been commented out, and therefore is not rendered in an IG

Note: the [layout template page for profiles](https://github.com/HL7/ig-template-base/blob/master/layouts/layout-profile.html) no longer includes a tab for `Text Summary`, so why would it still be present for extensions? Profiles now include this summary information in another tab called `Statistics/References`. This looks like a misalignment that hasn't yet been sorted out.

### 3. ./scripts
#### a) `ant-hl7.xml`
* triggered by `onGenerate`
* triggers `onGenerate.genProperties.xslt`
* something to do with JIRA spec artifacts

#### b) `onGenerate.genProperties.xslt`
* triggered by `onGenerate`
* appears to be running checks to ensure that the template can only be used in the Australian realm for HL7 IGs, otherwise it terminates the process 


#### c) `onGenerate.package-list.xslt`
* triggered by `onGenerate`
* something to do with processing the package list

