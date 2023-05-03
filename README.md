# rsl-component 

A reusable React component that simplifies the process of adding Region, State, and LGA selection drop-downs to forms in web applications. This helps developers by eliminating the need to build these inputs from scratch. 

🔗 **[Demo](https://rsl-component.netlify.app/)**

## Installation

Install this package with npm or yarn:

```bash
# If you use npm:
npm install rsl-component

# Or if you use Yarn:
yarn add rsl-component
```
    
## Usage

Import and use the InputRSL component in your React component.
```javascript
import InputRSL from 'rsl-component';

<InputRSL />
```

## Example
When you use the `InputRSL` component in your form, you can pass down the `selectedRegion`, `selectedState`, and `selectedLga` values as props, and also pass down the corresponding `handleRegionChange`, `handleStateChange`, and `handleLgaChange` callback functions to update the state when the user makes selections.

Here's an example of how you can use the `InputRSL` component in a form:

```javascript
import React, { useState } from 'react';
import InputRSL from 'rsl-component'; // Import the InputRSL component

const MyForm = () => {
  const [formData, setFormData] = useState({
    region: '',
    state: '',
    lga: '',
  });

  const handleFormSubmit = (e) => {
    e.preventDefault();
    // Access the selected values from the form data state
    const { region, state, lga } = formData;
    // Perform form submission with the selected values
    // ... Your form submission logic here ...
  };

  const handleRegionChange = (region) => {
    setFormData(prevFormData => ({ ...prevFormData, region }));
  };

  const handleStateChange = (state) => {
    setFormData(prevFormData => ({ ...prevFormData, state }));
  };

  const handleLgaChange = (lga) => {
    setFormData(prevFormData => ({ ...prevFormData, lga }));
  };

  return (
    <form onSubmit={handleFormSubmit}>
      {/* Render the InputRSL component with props and callbacks */}
      <InputRSL
        selectedRegion={formData.region}
        selectedState={formData.state}
        selectedLga={formData.lga}
        handleRegionChange={handleRegionChange}
        handleStateChange={handleStateChange}
        handleLgaChange={handleLgaChange}
      />
      {/* ...Other form inputs and submit button... */}
    </form>
  );
};

export default MyForm;

```

In this example, the `formData` state holds the values selected by the user in the `InputRSL` component, and the corresponding `handleRegionChange`, `handleStateChange`, and `handleLgaChange` callback functions are passed as props to the `InputRSL` component to update the form data state when the user makes selections. You can then access the selected values from the form data state (`formData.region`, `formData.state`, and `formData.lga`) and use them for your form submission logic.

## `showRegion` prop
The `showRegion` prop is a boolean that controls the visibility of the "Region" input field in the InputRSL component. If set to `true`, the "Region" input field will be displayed, and if set to `false`, the "Region" input field will be hidden.

**To use the** `showRegion` prop, simply pass it to the `InputRSL` component as a boolean prop. For example:
```javascript
<InputRSL showRegion={true} />

```
In this example, we're passing the `showRegion` prop with a value of `true`, which means that the "Region" input field will be displayed in the `InputRSL` component.

To hide the "Region" input field, simply set the showRegion prop to `false`:
```javascript
<InputRSL showRegion={false} />

```
In this example, we're passing the showRegion prop with a value of `false`, which means that the "Region" input field will be hidden in the `InputRSL` component.

**By default value**, the `showRegion` prop is set to `true`, which means that the "Region" input field will be displayed in the `InputRSL` component if the prop is not explicitly set to `false`.

**Take note that** if you set `showRegion` to `false`, the first input field will be hidden, and the remaining two input fields will shift up to take its place. If you set `showRegion` to `true`, the "Region" input field will be displayed, and the remaining two input fields will shift down to make space for it.

## Contributing

We welcome and appreciate contributions from the community to help improve the codebase and make it even better and simpler! Whether it's fixing bugs, adding new features, improving documentation, or enhancing performance, your contributions can make a significant impact on the project.

<!-- See `here` for ways to get started.

Please adhere to this project's `code of conduct`. -->


## Acknowledgements

`InputRSL` component was built with Vite and React, and it uses pre-defined data for regions, states, and LGAs in Nigeria. The original code was provided by the user.
## Spread the word

If you find our npm package useful, please help us spread the word! Share it with your colleagues, friends, and the wider community. This can help us attract more contributors and improve the project's visibility.

We appreciate your contributions in making our npm package better and simpler! Thank you for your support.


## License

This project is licensed under the [MIT](https://choosealicense.com/licenses/mit/) License. 

