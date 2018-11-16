# Overview

Formly simplifies form submission for your website. Set up a form, submit it to us and we'll send you all of the data in an email. No need for setting up a backend server or an email service. We take care of all of that for you.

## Setup

There are three ways to submit a form to us.

1\. Change the action of your form to point to us. You will need to set up a project on the Formly [site](https://formlyapp.com). You can find out more about projects in these docs [here](./projects.md).

```
<form action="https://post.formlyapp.com/your-project">
```

2\. Send form data to us asychronously as either JSON or as a serialized string. You will need to set up a project on the Formly [site](https://formlyapp.com).

```
$.ajax({
    url: 'https://post.formlyapp.com/your-project',
    type: 'POST',
    data: $('#my-form').serialize(),
    success: function (data) {
        alert('Submitted: ' + JSON.stringify(data));
    },
    error: function (xhr) {
        alert('Error: ' + JSON.stringify(xhr.responseText));
    }
});
```

3\. Use hidden form fields to submit forms to us anonymously. You don't need a project for this. You can also send these hidden configuration fields to us asychronously instead.

```
<form action="https://post.formlyapp.com/custom">
    ...
    <input type="hidden" name="config[to]" value="your@email.com"/>
    <input type="hidden" name="config[from]" value="your@website.com"/>
    <input type="hidden" name="config[subject]" value="My Website Form"/>
</form>
```
