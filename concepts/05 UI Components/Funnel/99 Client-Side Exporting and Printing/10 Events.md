DevExtreme data visualization UI components raise the following exporting-related events.

- [exporting](/api-reference/10%20UI%20Components/BaseWidget/4%20Events/exporting.md '/Documentation/ApiReference/UI_Components/dxFunnel/Events/#exporting')  
Allows you to request exporting details or prevent exporting.

- [exported](/api-reference/10%20UI%20Components/BaseWidget/4%20Events/exported.md '/Documentation/ApiReference/UI_Components/dxFunnel/Events/#exported')  
Allows you to notify an end user when exporting is completed.

- [fileSaving](/api-reference/10%20UI%20Components/BaseWidget/4%20Events/fileSaving.md '/Documentation/ApiReference/UI_Components/dxFunnel/Events/#fileSaving')        
Allows you to access exported data in the <a href="https://en.wikipedia.org/wiki/Binary_large_object" target="_blank">BLOB</a> format and/or prevent it from being saved in a file on the user's local storage.

You can handle these events with functions. If the handling functions are not going to be changed at runtime, assign them to the [onExporting](/api-reference/10%20UI%20Components/BaseWidget/1%20Configuration/onExporting.md '/Documentation/ApiReference/UI_Components/dxFunnel/Configuration/#onExporting'), [onExported](/api-reference/10%20UI%20Components/BaseWidget/1%20Configuration/onExported.md '/Documentation/ApiReference/UI_Components/dxFunnel/Configuration/#onExported') and [onFileSaving](/api-reference/10%20UI%20Components/BaseWidget/1%20Configuration/onFileSaving.md '/Documentation/ApiReference/UI_Components/dxFunnel/Configuration/#onFileSaving') properties when you configure the UI component.

---
##### jQuery

    <!--JavaScript-->$(function() {
        $("#funnelContainer").dxFunnel({
            // ...
            onExporting: function (e) {
                // Handler of the "exporting" event
            },
            onExported: function (e) {
                // Handler of the "exported" event
            },
            onFileSaving: function (e) {
                // Handler of the "fileSaving" event
            }
        });
    });


##### Angular

    <!--HTML--><dx-funnel ...
        (onExporting)="onExporting($event)"
        (onExported)="onExported($event)"
        (onFileSaving)="onFileSaving($event)">
    </dx-funnel>

    <!--TypeScript-->
    import { DxFunnelModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        onExporting (e) {
            // Handler of the "exporting" event
        };
        onExported (e) {
            // Handler of the "exported" event
        };
        onFileSaving (e) {
            // Handler of the "fileSaving" event
        }
    }
    @NgModule({
        imports: [
            // ...
            DxFunnelModule
        ],
        // ...
    })

##### Vue

    <!-- tab: App.vue -->
    <template> 
        <DxFunnel
            @exporting="onExporting"
            @exported="onExported"
            @file-saving="onFileSaving"
        />
    </template>

    <script>
    import DxFunnel from 'devextreme-vue/funnel';

    export default {
        components: {
            DxFunnel
        },
        methods: {
            onExporting (e) {
                // Handler of the "exporting" event
            };
            onExported (e) {
                // Handler of the "exported" event
            };
            onFileSaving (e) {
                // Handler of the "fileSaving" event
            }
        }
    }
    </script>

##### React

    <!-- tab: App.js -->
    import React from 'react';
    import Funnel from 'devextreme-react/funnel';

    class App extends React.Component {
        render() {
            return (
                <Funnel
                    onExporting={this.onExporting}
                    onExported={this.onExported}
                    onFileSaving={this.onFileSaving}
                />
            );
        }
        onExporting (e) {
            // Handler of the "exporting" event
        };
        onExported (e) {
            // Handler of the "exported" event
        };
        onFileSaving (e) {
            // Handler of the "fileSaving" event
        }
    }

    export default App;

---

---
##### jQuery

Otherwise, or if you need several handlers for a single event, subscribe to the exporting-related events using the [on(eventName, eventHandler)](/api-reference/10%20UI%20Components/Component/3%20Methods/on(eventName_eventHandler).md '/Documentation/ApiReference/UI_Components/dxFunnel/Methods/#oneventName_eventHandler') method. 

    <!--JavaScript-->
    var exportedHandler1 = function (e) {
        // First handler of the "exported" event
    };

    var exportedHandler2 = function (e) {
        // Second handler of the "exported" event
    };

    $("#funnelContainer").dxFunnel("instance")
        .on("exported", exportedHandler1)
        .on("exported", exportedHandler2);

---

#####See Also#####
#include common-link-handleevents