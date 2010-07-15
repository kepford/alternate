Preparation:
============
Have the class go to Administer >> Content >> Content types, and make the
following changes to the "Story" content type:

- Workflow settings: Turn on revisions
- Comment settings: Change location of the comment form to below post/comments.

Take-aways:
===========
hook_profile_alter():
- Mention how useful theme_image() is; it makes the image URL correct no 
  matter whether you're in a subdirectory, have clean URLs, are using private
  files, etc.

hook_form_FORM_ID_alter():
- Emphasize that it's important to respect the existing validation functions.
  dsm() the $form array to show that there's an existing $form['#validate']
  function. If you do:

  $form['#validate'] = array('mysite_user_register_validate');

  ...it will no longer check the username or email address for validity, and
  will let you pass through to submit, even if username is duplicate.

hook_views_data_alter():
- To do this one you actually have to have a view with a field that actually
  has the handler 'views_handler_field_numeric'. One is the comment count in
  the built-in tracker view.
- Also note that you actually have to go into the view and update the handler
  to "numerify". It doesn't just happen. You have to configure it.