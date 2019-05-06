# The Flow

The basic flow for an integrating application is as follows:

<aside class="notice">
We'll use some pseudo code here. <code>createThing(widget) -> url</code> means <i>use the <code>createThing</code> mutation or query, passing in a <code>widget</code>, and it will return a URL.</i>
Obviously the GraphQL doesn't work <i>quite</i> like that, but we'll look at specifics later on.
</aside>

## Creating and Editing Banks and Items, and Forms and Rules

You'll want an exam author to start creating content. To do this you need to create some banks and forms, and then create a URL to launch the editor and open it for the author. 

1. Use `createBank()` and `createForm()` to create banks and forms. Save the IDs if you need to, otherwise you can always use `banks()` and `forms()` queries to retrieve everything in your account.
2. Use `createEditorLaunchUrl(bankIds, formIds) -> url` to get a URL to open an interface to allow an exam author to edit the given banks (and items in them) and forms (and rules on them).
3. Give the URL bank to the client, probably opening an iframe or a new window. Nito takes over from there.

## Creating and Launching Exams

When a learner is ready to take an exam, you need to create an exam from a form, and then create a URL to launch the exam.

1. Use `createExam(formId) -> examId` to create an exam from a form based on the rules in the form. Hold onto the exam ID you get back.
2. Use `createExamLaunchUrl(examId) -> url` to get a URL to open an interface to the exam driver.
3. Give the URL back to the client, probably opening an iframe or a new window. Nito takes over from there.

## Reviewing Exams

When a learner has finished their exam, frequently somebody else might need to review that exam.

1. Use `createExamReviewLaunchUrl(examId) -> url` to get a URL to open an interface to the exam review screen.
2. Give the URL back to the client, probably opening an iframe or a new window. Nito takes over from there.
