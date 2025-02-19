The LoadPanel is an overlay UI component notifying the viewer that loading is in progress.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/LoadPanel/Overview/"
}

The following code adds to your page a simple LoadPanel and a [Button](/api-reference/10%20UI%20Components/dxButton '/Documentation/ApiReference/UI_Components/dxButton/') that invokes it. The [hideOnOutsideClick](/api-reference/10%20UI%20Components/dxOverlay/1%20Configuration/hideOnOutsideClick.md '/Documentation/ApiReference/UI_Components/dxLoadPanel/Configuration/#hideOnOutsideClick') property set to **true** instructs the LoadPanel to hide once a user clicks outside it.

---
##### jQuery

    <!--HTML--><div id="loadPanelContainer"></div>
    <div id="buttonContainer"></div>

    <!--JavaScript-->$(function() {
		$("#loadPanelContainer").dxLoadPanel({
            hideOnOutsideClick: true
        });
        
        $("#buttonContainer").dxButton({
            text: "Show the Load Panel", 
            onClick: function () {
                $("#loadPanelContainer").dxLoadPanel("show");
            } 
        });
    });

##### Angular

    <!--HTML-->
    <dx-load-panel
        [hideOnOutsideClick]="true"
        [(visible)]="isLoadPanelVisible">
    </dx-load-panel>
    <dx-button
        text="Show the Load Panel"
        (onClick)="isLoadPanelVisible = true">
    </dx-button>

    <!--TypeScript-->
    import { DxLoadPanelModule, DxButtonModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        isLoadPanelVisible: boolean = false;
    }
    @NgModule({
        imports: [
            // ...
            DxLoadPanelModule,
            DxButtonModule
        ],
        // ...
    })

##### Vue

    <template>
        <div>
            <DxLoadPanel
                :hide-on-outside-click="true"
                v-model:visible="isLoadPanelVisible"
            />
            <DxButton
                text="Show the Load Panel"
                @click="handleClick"
            />
        </div>
    </template>

    <script>
    import 'devextreme/dist/css/dx.light.css';

    import { DxLoadPanel } from 'devextreme-vue/load-panel';
    import { DxButton } from 'devextreme-vue/button';

    export default {
        components: {
            DxLoadPanel,
            DxButton
        },
        data() {
            return {
                isLoadPanelVisible: false
            }
        },
        methods: {
            handleClick() {
                this.isLoadPanelVisible = true;
            }
        }
    }
    </script>

##### React

    import React from 'react';
    import 'devextreme/dist/css/dx.light.css';

    import { LoadPanel } from 'devextreme-react/load-panel';
    import { Button } from 'devextreme-react/button';

    class App extends React.Component {
        constructor(props) {
            super(props);

            this.state = {
                isLoadPanelVisible: false
            };

            this.handleClick = this.handleClick.bind(this);
            this.handleHide = this.handleHide.bind(this);
        }

        handleClick() {
            this.setState({
                isLoadPanelVisible: true
            });
        }

        handleHide() {
            this.setState({
                isLoadPanelVisible: false
            });
        }

        render() {
            return (
                <div>
                    <LoadPanel
                        hideOnOutsideClick={true}
                        visible={this.state.isLoadPanelVisible}
                        onHidden={this.handleHide}
                    />
                    <Button
                        text="Show the Load Panel"
                        onClick={this.handleClick}
                    />
                </div>
            );
        }
    }

    export default App;

---

#####See Also#####
#include common-link-configurewidget
- [LoadPanel - Show and Hide Using the API](/concepts/05%20UI%20Components/LoadPanel/05%20Show%20and%20Hide%20Using%20the%20API.md '/Documentation/Guide/UI_Components/LoadPanel/Show_and_Hide_Using_the_API/')
- [LoadPanel - Customize the Appearance](/concepts/05%20UI%20Components/LoadPanel/10%20Customize%20the%20Appearance/10%20Customize%20the%20Loading%20Indicator.md '/Documentation/Guide/UI_Components/LoadPanel/Customize_the_Appearance/')
- [LoadPanel - Resize and Relocate](/concepts/05%20UI%20Components/LoadPanel/15%20Resize%20and%20Relocate.md '/Documentation/Guide/UI_Components/LoadPanel/Resize_and_Relocate/')
- [LoadPanel API Reference](/api-reference/10%20UI%20Components/dxLoadPanel '/Documentation/ApiReference/UI_Components/dxLoadPanel/')

[tags]dxloadpanel, loadPanel, load panel, overview, overlay