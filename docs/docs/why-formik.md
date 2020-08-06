---
id: why-formik
title: Why Formik
---

In the file no formik an example of a basic form has been set up to illistrate how much work goes into building a form and managing states.

A basic input starts out as an innocent 
```
<input name="name" type="text"/>
```
But quickly turn into something looking more like this

```
      <input
        name="name"
        value={state.name}
        onBlur={() => {
          validateName(state.name);
          setTouched({ name: true });
        }}
        onChange={(e) => {
          setState({ name: e.target.value });

          if (touched.name) {
            validateName(state.name);
          }
        }}
      />
```

The above is just some of the little events that gets tracked and used to manage the error/ touched/ and value state of a form input

This might not seem to bad, but code gets quite complex and unreadable very quickly

In the file `NoFormik.tsx` you can look at a basic example of a working form that tracks touched, error and value

In this file you can also see that a simple task of capturing 3 values turns into a mess of managing state.

### References

- https://reactjs.org/docs/forms.html
