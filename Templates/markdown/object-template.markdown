#{{page/title}}

{{#object/comment}}
{{#hasLongDescription}}
##{{strings/objectOverview/title}}
{{#longDescription}}{{>GBCommentComponentsList}}{{/longDescription}}
{{/hasLongDescription}}
{{/object/comment}}
					
{{#object/methods}}
{{#hasSections}}
##{{strings/objectTasks/title}}
{{#sections}}	
{{#sectionName}}{{.}}{{/sectionName}}
{{>TaskTitle}}
{{#methods}}{{>TaskMethod}}{{/methods}}
{{/sections}}
{{/hasSections}}
{{/object/methods}}
					
{{#object/methods}}
{{#hasProperties}}
##{{strings/objectMethods/propertiesTitle}}
{{#properties}}
{{>Method}}
{{/properties}}
{{/hasProperties}}

{{#hasClassMethods}}
##{{strings/objectMethods/classMethodsTitle}}
{{#classMethods}}
{{>Method}}
{{/classMethods}}
{{/hasClassMethods}}

{{#hasInstanceMethods}}
##{{strings/objectMethods/instanceMethodsTitle}}
{{#instanceMethods}}
{{>Method}}
{{/instanceMethods}}
{{/hasInstanceMethods}}
{{/object/methods}}

Section Method
###`{{methodSelector}}`
{{#comment}}
{{#hasShortDescription}}
{{#shortDescription}}{{>GBCommentComponent}}{{/shortDescription}}
{{/hasShortDescription}}
	
`{{>MethodDeclaration}}`
	
{{#hasMethodParameters}}
###{{strings/objectMethods/parametersTitle}}
{{#methodParameters}}
`{{argumentName}}`
{{#argumentDescription}}{{>GBCommentComponentsList}}{{/argumentDescription}}
{{/methodParameters}}
{{/hasMethodParameters}}

{{#hasMethodResult}}
###{{strings/objectMethods/resultTitle}}
{{#methodResult}}{{>GBCommentComponentsList}}{{/methodResult}}
{{/hasMethodResult}}

{{#hasAvailability}}
###{{strings/objectMethods/availability}}
{{#availability}}{{>GBCommentComponentsList}}{{/availability}}
{{/hasAvailability}}

{{#hasLongDescription}}
###{{strings/objectMethods/discussionTitle}}
{{#longDescription}}{{>GBCommentComponentsList}}{{/longDescription}}
{{/hasLongDescription}}

{{#hasMethodExceptions}}
###{{strings/objectMethods/exceptionsTitle}}
{{#methodExceptions}}
`{{argumentName}}`
{{#argumentDescription}}{{>GBCommentComponentsList}}{{/argumentDescription}}
{{/methodExceptions}}
{{/hasMethodExceptions}}

{{#hasRelatedItems}}
###{{strings/objectMethods/seeAlsoTitle}}
{{#relatedItems/components}}
* `{{>GBCommentComponent}}`
{{/relatedItems/components}}
{{/hasRelatedItems}}

{{#prefferedSourceInfo}}
###{{strings/objectMethods/declaredInTitle}}
`{{filename}}`		
{{/prefferedSourceInfo}}
{{/comment}}
EndSection

Section MethodDeclaration
{{#formattedComponents}}{{value}}{{/formattedComponents}}
EndSection


Section TaskTitle
{{#hasMultipleSections}}
{{#sectionName}}{{.}}{{/sectionName}}
{{^sectionName}}{{strings/objectTasks/otherMethodsSectionName}}{{/sectionName}}
{{/hasMultipleSections}}
{{^hasMultipleSections}}
{{#sectionName}}
###{{.}}
{{/sectionName}}
{{/hasMultipleSections}}
EndSection

Section TaskMethod
`{{>TaskSelector}}`

{{#comment}}{{#hasShortDescription}}
{{#shortDescription}}{{>GBCommentComponent}}{{/shortDescription}}{{/hasShortDescription}}{{/comment}}

{{#isProperty}}{{strings/objectTasks/property}}{{/isProperty}}
{{#isRequired}} {{strings/objectTasks/requiredMethod}}{{/isRequired}}
EndSection

Section TaskSelector
{{#isInstanceMethod}}-{{/isInstanceMethod}}{{#isClassMethod}}+{{/isClassMethod}}{{#isProperty}}{{/isProperty}}{{methodSelector}}
EndSection


Section GBCommentComponentsList
{{#components}}{{>GBCommentComponent}}{{/components}}
EndSection

Section GBCommentComponent
{{&htmlValue}}
EndSection