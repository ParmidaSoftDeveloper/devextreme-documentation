When a user types a value into the TextBox, this value applies when the <a href="https://developer.mozilla.org/en/docs/Web/Events/change" target="_blank">change</a> event is raised. If you need the value to be applied on another event, set the [valueChangeEvent](/api-reference/10%20UI%20Components/dxTextEditor/1%20Configuration/valueChangeEvent.md '/Documentation/ApiReference/UI_Components/dxTextBox/Configuration/#valueChangeEvent') property.

---
##### jQuery

    <!--JavaScript-->$(function() {
        $("#textBoxContainer").dxTextBox({
            valueChangeEvent: "keyup"
        });
    });

##### Angular

    <!--HTML-->
    <dx-text-box
        valueChangeEvent="keyup">
    </dx-text-box>

    <!--TypeScript-->
    import { DxTextBoxModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        // ...
    }
    @NgModule({
        imports: [
            // ...
            DxTextBoxModule
        ],
        // ...
    })

##### Vue

    <template>
        <DxTextBox value-change-event="keyup"/>
    </template>

    <script>
    import 'devextreme/dist/css/dx.light.css';

    import { DxTextBox } from 'devextreme-vue/text-box';

    export default {
        components: {
            DxTextBox
        }
    }
    </script>

##### React

    import React from 'react';
    import 'devextreme/dist/css/dx.light.css';

    import { TextBox } from 'devextreme-react/text-box';

    class App extends React.Component {
        render() {
            return (
                <TextBox
                    valueChangeEvent="keyup"
                />
            );
        }
    }

    export default App;

---

To process a new TextBox value, you need to handle the value change event. If the handling function is not going to be changed during the lifetime of the UI component, assign it to the [onValueChanged](/api-reference/10%20UI%20Components/dxTextEditor/1%20Configuration/onValueChanged.md '/Documentation/ApiReference/UI_Components/dxTextBox/Configuration/#onValueChanged') property when you configure the UI component.

---
##### jQuery

    <!--JavaScript-->$(function() {
        $("#textBoxContainer").dxTextBox({
            onValueChanged: function (e) {
                const previousValue = e.previousValue;
                const newValue = e.value;
                // Event handling commands go here
            }
        });
    });

##### Angular

    <!--HTML-->
    <dx-text-box
        [(value)]="textBoxValue"
        (onValueChanged)="handleValueChange($event)">
    </dx-text-box>

    <!--TypeScript-->
    import { DxTextBoxModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        textBoxValue = "The TextBox value";

        handleValueChange(e) {
            const previousValue = e.previousValue;
            const newValue = e.value;
            // Event handling commands go here
        }
    }
    @NgModule({
        imports: [
            // ...
            DxTextBoxModule
        ],
        // ...
    })

##### Vue

    <template>
        <DxTextBox
            v-model:value="textBoxValue"
            @value-changed="handleValueChange"
        />
    </template>

    <script>
    import 'devextreme/dist/css/dx.light.css';

    import { DxTextBox } from 'devextreme-vue/text-box';

    export default {
        components: {
            DxTextBox
        },
        data() {
            return {
                textBoxValue: "The TextBox value"
            };
        },
        methods: {
            handleValueChange(e) {
                const previousValue = e.previousValue;
                const newValue = e.value;
                // Event handling commands go here
            }
        }
    }
    </script>

##### React

    import React from 'react';
    import 'devextreme/dist/css/dx.light.css';

    import { TextBox } from 'devextreme-react/text-box';

    class App extends React.Component {
        constructor(props) {
            super(props);

            this.state = {
                textBoxValue: "The TextBox value"
            };

            this.handleValueChange = this.handleValueChange.bind(this);
        }

        handleValueChange(e) {
            const previousValue = e.previousValue;
            const newValue = e.value;

            this.setState({
                textBoxValue: newValue
            });
        }

        render() {
            return (
                <TextBox
                    value={this.state.textBoxValue}
                    onValueChanged={this.handleValueChange}
                />
            );
        }
    }

    export default App;

---

---

##### jQuery

If you are going to change event handlers at runtime, or if you need to attach several handlers to the value change event, subscribe to this event using the [on(eventName, eventHandler)](/api-reference/10%20UI%20Components/Component/3%20Methods/on(eventName_eventHandler).md '/Documentation/ApiReference/UI_Components/dxTextBox/Methods/#oneventName_eventHandler') method.

    <!--JavaScript-->
    const valueChangedHandler1 = function (e) {
        const previousValue = e.previousValue;
        const newValue = e.value;
        // First handler of the "valueChanged" event
    };

    const valueChangedHandler2 = function (e) {
        const previousValue = e.previousValue;
        const newValue = e.value;
        // Second handler of the "valueChanged" event
    };

    $("#textBoxContainer").dxTextBox("instance")
        .on("valueChanged", valueChangedHandler1)
        .on("valueChanged", valueChangedHandler2);

---

#####See Also#####
#include common-link-handleevents
- [TextBox - Handle the Keyboard Events](/concepts/05%20UI%20Components/TextBox/13%20Handle%20the%20Keyboard%20Events.md '/Documentation/Guide/UI_Components/TextBox/Handle_the_Keyboard_Events/')
- [TextBox Demos](https://js.devexpress.com/Demos/WidgetsGallery/Demo/TextBox/Overview)
- [TextBox API Reference](/api-reference/10%20UI%20Components/dxTextBox '/Documentation/ApiReference/UI_Components/dxTextBox/')

[tags]textBox, text box, editor, get value, set value, change value, valueChangeEvent, valueChanged