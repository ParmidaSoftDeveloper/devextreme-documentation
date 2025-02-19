The focused row feature allows you to display master-detail relationships and improve navigation through records.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/DataGrid/FocusedRow/"
}

To allow users to focus rows, set the [focusedRowEnabled](/api-reference/10%20UI%20Components/GridBase/1%20Configuration/focusedRowEnabled.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#focusedRowEnabled') property to **true**.

Users can control the focused row using the following mouse and keyboard commands:

<table class="dx-table">
    <tr>
        <th style="width:25%;">Command</th><th>Action</th>
    </tr>
    <tr>
        <td>Mouse Click</td><td>Focuses a row.</td>
    </tr>
    <tr>
        <td>&uarr; / &darr;</td>
        <td>Focuses the next/previous row.</td>
    </tr>
    <tr>
        <td>&larr; / &rarr;</td>
        <td>Focuses the cell to the left/right.</td>
    </tr>
    <tr>
        <td>Esc</td>
        <td>Removes highlighting from the focused cell.</td>
    </tr>
</table>

You can specify the initially focused row using the [focusedRowKey](/api-reference/10%20UI%20Components/GridBase/1%20Configuration/focusedRowKey.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#focusedRowKey') or [focusedRowIndex](/api-reference/10%20UI%20Components/GridBase/1%20Configuration/focusedRowIndex.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#focusedRowIndex') property. The grid is scrolled down to it. If you also set the [focusedColumnIndex](/api-reference/10%20UI%20Components/GridBase/1%20Configuration/focusedColumnIndex.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#focusedColumnIndex') property, a specific cell in this row is focused.

---
##### jQuery

    <!--JavaScript-->
    $(function() {
        $("#dataGridContainer").dxDataGrid({
            // ...
            focusedRowEnabled: true,
            focusedRowIndex: 0, // focus the first row
            // or
            // focusedRowKey: 100,
            focusedColumnIndex: 0 // focus the first cell
        });
    });

##### Angular

    <!--HTML-->
    <dx-data-grid ...
        [focusedRowEnabled]="true"
        [focusedRowIndex]="0" <!-- focus the first row -->
        [focusedColumnIndex]="0"> <!-- focus the first cell -->
    </dx-data-grid>

    <!--TypeScript-->
    import { DxDataGridModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        // ...
    }
    @NgModule({
        imports: [
            // ...
            DxDataGridModule
        ],
        // ...
    })

##### Vue

    <!-- tab: App.vue -->
    <template>
        <DxDataGrid ...
            :focused-row-enabled="true"
            :focused-row-index="0" <!-- focus the first row -->
            :focused-column-index="0"> <!-- focus the first cell -->
        </DxDataGrid>
    </template>

    <script>
    import 'devextreme/dist/css/dx.light.css';

    import DxDataGrid from 'devextreme-vue/data-grid';

    export default {
        components: {
            DxDataGrid
        },
        // ...
    }
    </script>

##### React

    <!-- tab: App.js -->
    import React from 'react';
    import 'devextreme/dist/css/dx.light.css';

    import DataGrid from 'devextreme-react/data-grid';

    export default function App() {
        return (
            <DataGrid ...
                focusedRowEnabled={true}
                focusedRowIndex={0} {/* focus the first row */}
                focusedColumnIndex={0}> {/* focus the first cell */}
            </DataGrid>
        );
    }

---

---
##### jQuery

Change the same properties using the [option(optionName, optionValue)](/api-reference/10%20UI%20Components/Component/3%20Methods/option(optionName_optionValue).md '/Documentation/ApiReference/UI_Components/dxDataGrid/Methods/#optionoptionName_optionValue') method to focus a row or cell programmatically. You can also use the [navigateToRow(key)](/api-reference/10%20UI%20Components/GridBase/3%20Methods/navigateToRow(key).md '/Documentation/ApiReference/UI_Components/dxDataGrid/Methods/#navigateToRowkey') method to focus a row.

    <!--JavaScript-->
    var dataGrid = $("#dataGridContainer").dxDataGrid("instance");
    dataGrid.option("focusedRowKey", 100);
    // or
    dataGrid.navigateToRow(100);

---

The DataGrid raises events before and after a row or cell is focused. Use the [onFocusedRowChanging](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onFocusedRowChanging.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#onFocusedRowChanging')/[onFocusedRowChanged](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onFocusedRowChanged.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#onFocusedRowChanged') and [onFocusedCellChanging](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onFocusedCellChanging.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#onFocusedCellChanging')/[onFocusedCellChanged](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onFocusedCellChanged.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#onFocusedCellChanged') functions to handle these events. You can perform custom actions in these functions, for instance, customize keyboard navigation, as shown in the [onFocusedCellChanging](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onFocusedRowChanging.md '/Documentation/ApiReference/UI_Components/dxDataGrid/Configuration/#onFocusedRowChanging') example.
