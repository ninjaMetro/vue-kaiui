# kaiui-radiobutton 

The `<kaiui-radiobutton>` component. 

- **author** - Sebastian Baar 
- **license** - MIT 

## props 

- `softkeys` ***{ left: String, center: String, right: String }*** (*optional*) `default: { center: "Select" }` 

  The Softkeys Object 

- `value` ***String*** (*required*) 

  The Value 

- `primary-text` ***String*** (*required*) 

  The Primary Text 

- `secondary-text` ***String*** (*optional*) 

  The Secondary Text 

## events 

- `radiobutton-mounted` 

- `softLeft` 

  Emit the event `softLeft` when left softkey is selected 

- `softRight` 

  Emit the event `softRight` when right softkey is selected 

- `radiobutton-selected` 

- `softCenter` 

  Emit the event `softCenter` when center softkey is selected 

- `update-softkeys-register` 

- `update-softkeys-unregister` 

- `set-element-selected` 

