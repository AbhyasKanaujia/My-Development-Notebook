# Forms



## Basics

### Form.Control

The `<Form.Control>` component renders a form control with Bootstrap styling.

### Form.Group

The `<Form.Group>` component wraps a form control with proper spacing, along with support for a label, help text, and validation state.&#x20;

* To ensure accessibility, set `controlId` on `<FormGroup>`, and use `<FormLabel>` for the label.

```jsx
<Form>
  <Form.Group className='mb-3' controlId='email'>
    <Form.Label>Email address</Form.Label>
    <Form.Control type='email' placeholder='Enter email'/>
    <Form.Text>We'll never share your email with anyone else.</Form.Text>
  </Form.Group>
  
  <Form.Group className='mb-3' controlId='password'>
    <Form.Label>Password</Form.Label>
    <Form.Control type='password'/>  
  </Form.Group>
  
  <Form.Group className='mb-3' controlId='checkbox>
    <Form.Check type='checkbox' label='Remeber me'/>  
  </Form.Group>
  
  <Button variant='primary' type='submit'>Login</Button>
</Form>
```

![](<../../../.gitbook/assets/image (8).png>)



* If an app has too many form groups, a separate component can be created and appropriate props can be passed.&#x20;

### Disable Form

Just pass boolean `disabled` to any form control.

```jsx
<Form.Group>
    <Form.Label>Disabled input</Form.Label>
    <Form.Control disabled />
</Form.Group>
```

