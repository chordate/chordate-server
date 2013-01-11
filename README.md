#Chordate API

##Events
####Any error along with pertinent metadata (typically an application exception).

<table>
  <tr>
    <td>Field</td>
    <td>Required</td>
    <td>Data Type</td>
    <td>Example Values</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>created_at</td>
    <td>Yes</td>
    <td>Integer</td>
    <td>1357882938</td>
    <td>Time timestamp of when the culprit was generated</td>
  </tr>
  <tr>
    <td>env</td>
    <td>Yes</td>
    <td>String</td>
    <td>demo, staging, production</td>
    <td>The environment where the error occurred</td>
  </tr>
  <tr>
    <td>class</td>
    <td>Yes</td>
    <td>String</td>
    <td>StandardError, ActiveRecord::RecordNotUnique</td>
    <td>Typically the class of the error. Errors are grouped by class</td>
  </tr>
  <tr>
    <td>message</td>
    <td>Yes</td>
    <td>String</td>
    <td>Couldn't find User with id=6823</td>
    <td>The message associated with the error</td>
  </tr>
  <tr>
    <td>model_type</td>
    <td>No</td>
    <td>String</td>
    <td>User, Post, Message, Comment</td>
    <td>A model class that is relevant to the error: eg. when a background task is processing a certain record</td>
  </tr>
  <tr>
    <td>model_id</td>
    <td>No</td>
    <td>String</td>
    <td>10, 6823</td>
    <td>The id of model_type class that was relevant to the error</td>
  </tr>
  <tr>
    <td>backtrace</td>
    <td>No</td>
    <td>Array</td>
    <td>["/../app/models/user.rb:12:in `update'", "/../app/models/user.rb:36:in `get_post_data'"]</td>
    <td>The backtrace associated with the error (Maximum length of 25)</td>
  </tr>
  <tr>
    <td>environment</td>
    <td>No</td>
    <td>Hash</td>
    <td>{"hostname": "app1.local", "app_root": "/path/to/app"}</td>
    <td>The full environment with hostname, app root, etc</td>
  </tr>
  <tr>
    <td>extra</td>
    <td>No</td>
    <td>Hash</td>
    <td>{"params": {"action": "create", "name": "Bob"}, "extra": "info"}</td>
    <td>Any and all extra information</td>
  </tr>
  <tr>
    <td>action</td>
    <td>No</td>
    <td>String</td>
    <td>Sending email to a user group. Updating the cache.</td>
    <td>A human readable description of what was what was going on when erroring</td>
  </tr>
</table>

####Example
