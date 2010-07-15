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

