# Что такое редактор манифеста IIIF 

The aim of the IIIF Manifest Editor is to reduce the guess work and pure JSON editing when creating and/or manipulating manifests. It features a simple and easy-to-use interface with forms to edit the JSON value-pairs and drag-and-drop of images/canvases to facilitate the ordering and editing of the manifest without JSON knowledge. It will let you validate and download the created/modified IIIF manifest.


Цель редактора манифеста IIIF - создавать из IIIF изображений манифесты и / или производить различные действия с уже готовыми манифестами. Редактор имеет простой и удобный интерфейс с формами для редактирования и перетаскивания изображений / холстов для облегчения упорядочивания и редактирования манифестов без знания JSON.  Редактор также позволит вам проверить и загрузить созданный / измененный манифест IIIF. 

# Установка
См. Инструкции по установке файла README на Github: 
https://github.com/bodleian/iiif-manifest-editor/

# Open and modify an existing IIIF manifest
The start page of the application allows you to choose between creating a new manifest from scratch or open an existing manifest. Click on the "Open Manifest" button:
Открыть и изменить существующий манифест IIIF Стартовая страница приложения позволяет вам выбирать между созданием нового манифеста с нуля или открытием существующего манифеста.  Нажмите кнопку «Открыть манифест»: 

![Start Page](https://user-images.githubusercontent.com/725398/28833494-c9c3e872-76df-11e7-8499-4840a6efd5d6.png)

## Open a remote or local manifest
To load a remote manifest, insert the URL for the remote manifest to load and click on the "Open" button.

Alternatively, click on the "Choose File" button in the "From Computer" form field, this will let you choose a local file from your computer. Select a IIIF manifest (JSON) file from your computer and click on the "Open" button:

![Open remote manifest or upload local manifest](https://user-images.githubusercontent.com/725398/28833499-cec727e4-76df-11e7-966f-0ebad81d2e70.png)

You can also drag & drop a manifest file onto the gray area to load it.

## Discover manifests
Click on the "Discover Manifests" button to see a list of content providers:

![Content Providers](https://user-images.githubusercontent.com/725398/28833513-d46f520c-76df-11e7-96ea-86da62467342.png)

Then click on a content provider to get a list of manifests. Some content providers group their manifests into sub-collections in which case you can browse the sub-collections, click on a sub-collection and then browse the manifests in that sub-collection. Type a search query into the "Filter manifests" input field to filter the list of manifests:

![Filter manifests](https://user-images.githubusercontent.com/725398/28833521-d9d9cfba-76df-11e7-9112-fa771dad8213.png)


## Modify an existing manifest
Once the remote or local manifest is loaded you will see the "Edit Manifest" page:

![Edit Manifest Page](https://cloud.githubusercontent.com/assets/725398/21155319/03fef050-c172-11e6-9253-c19b69c4c837.png)

The "Edit Manifest" page contains the following main sections:
* Main viewer (top left): view, zoom and pan current canvas, navigate through sequence, toggle metadata sidebar
* Thumbnail strip (bottom left): view canvases and navigate through sequence. Drag canvases to reorder sequence
* Action buttons (top right): create new manifest, open another manifest, download and validate current manifest (save) and close current manifest, import canvases from other manifests
* Metadata sidebar: view and edit manifest metadata. Add, remove and edit metadata for the manifest level, the sequence level and the canvas level
* Bulk Actions: Bulk rename canvases in the current sequence

### The Manifest Metadata Panel

The "Manifest Metadata" panel has two tabs:

* Predefined fields and 
* Custom fields

**Predefined fields** are top-level manifest metadata properties such as label, description, attribution etc. To remove a property, click on the "x" button to the right of each property box. To add a property, click on the "Add metadata field" button. This will open a drop-down menu that lets you choose from a number of predefined fields. Only fields that are not yet added to the current manifest will be available for selection. Editable fields have a "pencil" icon. Click on the field value to edit it.

![Manifest Metadata Panel - Predefined Fields](https://cloud.githubusercontent.com/assets/725398/21190030/c68f1cf4-c220-11e6-9f7f-574936787153.png)

**Custom fields** are value/label pairs that will be stored in the "metadata" section of the manifest. Click the "Add metadata field button" to add a custom field. This will add a new box with "Label" for the label of the new property and "Value" for the value:

![Manifest Metadata - Custom fields](https://cloud.githubusercontent.com/assets/725398/21190126/23820714-c221-11e6-9beb-d2ca117da49c.png)

To edit the label or the value, click on it, replace the default text of "Label" or "Value" with the name for the metadata field (e.g. "Date") and hit enter.

### The Sequence Metadata Panel

The Sequence Metadata panel lets you edit the label for the current sequence and set the viewing direction for the manifest. Use the drop-down menu to toggle between left-to-right and right-to-left. The selected viewing direction will be added to the manifest level _viewingDirection_ property. You can also edit this in the Manifest Metadata panel directly. If _right-to-left_ has been selected, the sequence in the thumbnail strip will scroll to the last canvas in the sequence. If _left-to-right_ has been selected, the sequence in the thumbnail strip will scroll to the first canvas in the sequence. This setting only affects the *display* of the canvases in the thumbnail strip and does not actually reverse the *order* of the canvases in the manifest itself.

![Sequence Metadata Panel](https://cloud.githubusercontent.com/assets/725398/21190305/9e88d9e2-c221-11e6-84b7-d39e5a3ab031.png)

### The Canvas Metadata Panel

The Canvas Metadata panel shows the metadata for the selected canvas. You can edit the canvas label, the width and the height of the canvas and the image URI for the image that is annotated to the selected canvas:

![Canvas Metadata Panel](https://cloud.githubusercontent.com/assets/725398/21190407/ee57235c-c221-11e6-8009-e01f2a28ee77.png)

Empty canvases will show a "Add Image to Canvas" button underneath the thumbnail of the canvas, if the canvas already has an image annotation the button will say "Replace Image on Canvas". Clicking this button will open a modal window that lets you add or replace an image using either an image URI, an info.json URI or an existing image annotation:

![Add or Replace Image on Canvas](https://cloud.githubusercontent.com/assets/725398/19859751/b5b77636-9f86-11e6-9a0f-cb6fd2906fb7.png)

Click on the "Help" link on the top right of the modal window to learn more about each of the 3 options.

### Bulk Actions Panel

In the Bulk Actions panel you can perform actions that affect all canvases in the sequence. There are 3 actions you can perform:

* Reverse the order of the canvases in the sequence. This will not just affect the display of the sequence but also update the order of the canvases in the manifest 
* Automatically rename all canvas labels in the sequence by pagination. A drop-down menu lets you select a canvas from which to start the bulk renaming process (default is the first canvas in the sequence)
* Automatically rename all canvas labels in the sequence by foliation. A drop-down menu lets you select a canvas from which to start the bulk renaming process (default is the first canvas in the sequence), you can choose whether to start with a recto or a verso page

![Bulk Actions Panel](https://cloud.githubusercontent.com/assets/725398/21156035/a8c05122-c174-11e6-9a8b-35a7d759c0fc.png)

### Working with the Thumbnail Strip

The thumbnail strip at the bottom of the viewer shows the current sequence. Click on a thumbnail to select the canvas and display it in the viewer as well as its metadata in the Canvas Metadata panel. A canvas can be deleted by clicking the trash icon on the top left of each canvas. Use Shift + click to select multiple (adjacent) canvases and delete all at once:

![Deleting Multiple Canvases](https://cloud.githubusercontent.com/assets/725398/21190515/5776d620-c222-11e6-9269-7e2df4a8f373.png)

Clicking the icon on the top right of each canvas reveals a context menu that lets you:

* add an empty canvas to the left of the current canvas
* add an empty canvas to the right of the current canvas
* duplicate the current canvas
* go to "Import Canvases" view (see below)

![Canvas Options](https://cloud.githubusercontent.com/assets/725398/19859753/b64ca6fc-9f86-11e6-97bc-03957dc56d0d.png)

At the right end of the sequence there is an "Add Canvas" button which lets you add a canvas to the end of the sequence. Use the Canvas Metadata panel to add an image to an empty canvas using the "Add Image to Canvas" button.

Drag and drop a canvas within the thumbnail strip to change its location within the sequence.

## Import Canvases from Other Manifests

To go to the "Import Canvases" view you can use the context menu on each canvas or the "Manifest Actions" drop-down menu on the top right of the metadata sidebar. Click the "Open Sequence" button on the top left of the metadata sidebar to open a remote manifest:

![Import Canvases View](https://cloud.githubusercontent.com/assets/725398/21190617/b55862ae-c222-11e6-9def-e3f56341d233.png)

Enter a URI for the remote manifest you would like to load. You can open as many remote manifests next to each other as you like. The view is horizontally scrollable. Click the "x" button on the top right of each sequence to remove a sequence.

![Import Canvases - Multiple Sequences](https://cloud.githubusercontent.com/assets/725398/21190795/6109cb06-c223-11e6-9d6e-c68c16061d93.png) 

The displayed sequences on the top will act as "source" manifests. Each source manifest has its own viewer. Hover over the main image of a source manifest viewer to display its thumbnail strip with the sequence. The sequence in the thumbnail strip on the bottom is the "target" manifest (the one you are editing). To add a canvas from a source manifest to the target manifest simply drag & drop the canvas from the source to the target (i.e. from one of the thumbnail strips in the source manifests to the thumbnail strip on the bottom). Shift + click to select multiple (adjacent) canvases from a source manifest and drag them to the target to add multiple canvases at once.

Click the "i" icon on the top left of each source manifest to view the source manifest metadata:

![Source Manifest Metadata](https://cloud.githubusercontent.com/assets/725398/21190967/fdc74400-c223-11e6-9ec4-d5e1eee71eb2.png)

### Save / Download Manifest

Use the "Save Manifest" button on the top left of the metadata sidebar to download the created / edited manifest. A dialog will let you choose a name for your manifest and you can validate it before downloading it:

![Save and Validate Manifest](https://cloud.githubusercontent.com/assets/725398/19859762/b726b23e-9f86-11e6-81c3-7f7232b00f5b.png)


## Creating a new manifest
To create a new manifest from scratch instead of editing an existing one, select the "New Manifest" option from the "Manifest Actions" drop-down menu on the top right of the metadata sidebar.
You will be prompted if you would like to proceed or cancel and download your modified manifest first. After confirming, you will be presented with an empty "skeleton" manifest without any canvases plus some placeholder metadata.

Edit the metadata for the new manifest in the metadata sidebar by clicking on the placeholder text or adding a new metadata field. Add a new canvas by clicking on the "Add Canvas" button in the thumbnail strip. This will add an empty canvas that can then be updated with a label or image annotation in the Canvas Metadata of the sidebar.

![New Manifest](https://cloud.githubusercontent.com/assets/725398/21191431/5ba4a490-c225-11e6-806b-6fa7f4a1098e.png)
