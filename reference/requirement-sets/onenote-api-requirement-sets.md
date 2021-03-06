# OneNote JavaScript API requirement sets

Requirement sets are named groups of API members. Office Add-ins use requirement sets specified in the manifest or use a runtime check to determine whether an Office host supports APIs that an add-in needs. For more information, see [Specify Office hosts and API requirements](../../docs/overview/specify-office-hosts-and-api-requirements.md).

The following table lists the OneNote requirement sets, the Office host applications that support those requirement sets, and the build versions or availability date.

|  Requirement set  |  Office Online | 
|:-----|:-----|
| OneNoteApi 1.1  | September 2016 |  

## Office common API requirement sets
For information about common API requirement sets, see [Office common API requirement sets](office-add-in-requirement-sets.md).

## OneNote JavaScript API 1.1 
OneNote JavaScript API 1.1 is the first version of the API. For details about the API, see the [OneNote JavaScript API](../../docs/onenote/onenote-add-ins-programming-overview.md) reference topics.

## Runtime requirement support check

During the runtime, add-ins can check if a particular host supports an API requirement set by doing the following-check: 

```js
if (Office.context.requirements.isSetSupported('OneNoteApi', 1.3) === true) {
  /// perform actions
}
else {
  /// provide alternate flow/logic
}
```

## Manifest based requirement support check

Use the Requirements element in the add-in manifest to specify critical requirement sets or API members that your add-in must use. If the Office host or platform doesn't support the requirement sets or API members specified in the Requirements element, the add-in won't run in that host or platform, and won't display in My Add-ins.

The following code example shows an add-in that loads in all Office host applications that support OneNoteApi requirement set, version 1.1.

```xml
<Requirements>
   <Sets DefaultMinVersion="1.1">
      <Set Name="OneNoteApi" MinVersion="1.1"/>
   </Sets>
</Requirements>
```



## Additional resources

- [Specify Office hosts and API requirements](../../docs/overview/specify-office-hosts-and-api-requirements.md)
- [Office Add-ins XML manifest](../../docs/overview/add-in-manifests.md)
