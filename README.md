# Oban Website User guide

This is the user guide and conventions of the Oban Website found at http://www.obandigital.com.

## Table of contents

  - [Forms](#forms)
    - [Creating a thank you page](#creating-a-thank-you-page)
    - [Creating a form](#creating-a-form)
    - [Linking into a post](#linking-into-a-post) OR
    - [Creating a form page](#creating-a-form-page)

## Forms

[Top](#oban-website-user-guide)

Forms comprise of:

- a thank you page
- a form, added in Forms (Gravity Forms)
- a shortcode added to a post

### Login

- Login to the production site.
- Select the correct site e.g. `Oban UK` from the `My Sites` dropdown.

### Creating a thank you page

[Top](#oban-website-user-guide)

- Select `Pages` from the left hand navigation.
- This will show a list of all the pages.
- Select `Add New` to create a new page
- Set the fields according to the [conventions](#thank-you-page-conventions)
  - Parent in the right hand navigation to `Thank You`
  - Name to `Thank You - {{form name}}`
  - Body to (updating the name and link)
    - UK:

    ``` html
    [vc_row][vc_column][vc_column_text]
    Thank you for completing the form.
    Please click the download link below to access your {{name}}.
    <a href="http://www.obandigital.com/gb/wp-content/uploads/sites/3/2015/05/{{/path/to//uploaded/file.pdf}}">{{name}}</a>
    For further information please contact Oban Digital on <a href="tel:+44 (0) 1273 613 400">+44 (0) 1273 613 400</a> or email <a href="mailto:info@obandigital.com">info@obandigital.com</a>.
    [/vc_column_text][/vc_column][/vc_row]
    ```

    - US:

    ``` html
    [vc_row][vc_column][vc_column_text]
    Thank you for completing the form.
    Please click the download link below to access your {{name}}.
    <a href="http://www.obandigital.com/us/wp-content/uploads/sites/2/{{/path/to//uploaded/file.pdf}}">{{name}}</a>
    For further information please contact Oban Digital on <a href="tel:888.815.4494">888.815.4494</a> or email <a href="mailto:info@obandigitalusa.com">info@obandigitalusa.com</a>.
    [/vc_column_text][/vc_column][/vc_row]
    ```

  - All in One SEO Pack Title to a friendly title if required (overrides the name when viewing)
- Select Publish

#### Thank you page conventions

Thank you pages must have the:

- parent page set to
  ```
  Thank You
  ```
- title set to
  ```
  Thank You - {{form name}}
  ```
  e.g.
  ```
  Thank You - Download: Whitepaper 10 Key Dates
  ```
- Optionally: All in One SEO Pack title set to friendly text e.g.:
  ```
  Thanks! Download your whitepaper.
  ```

### Creating a form

[Top](#oban-website-user-guide)

- Select `Forms` from the left hand navigation.
- This will show a list of all the forms.

#### EITHER: Duplicate existing

- Hover over the title of an existing form that matches your fields
- Select Duplicate
- Click on the new form title to go to the form editor
- Note the ID underneath the title
- Update the [Form Settings](#form-settings)

#### OR: Add new

- Select `Add New` to create a new form
- Add a form title according to the [conventions](#contact-form-conventions) and click `Create Form`
- This will take you to the form editor

##### Form editor

- Click on `Single Line Text` under `Standard Fields` on the right hand navigation to add a simple text field
- Click on Untitled to show the field settings
- Update `Field Label` from `Untitled` to `Full Name` and tick `Required`
- Click the `Appearance` tab. Update Placeholder to `Full Name`. Note the Custom CSS Class field, which can be set to
  - empty for a full width field
  - `gf_left_half` to show the field on the left
  - `gf_right_half` to show the field on the right
- For contact forms add the following fields:
  - Single Line Text: Field Label: `Full Name`, Required: `ticked`, Placeholder: `Full Name`
  - Single Line Text: Field Label: `Company`,   Required: `ticked`, Placeholder: `Company`,   Custom CSS Class: `gf_left_half`
  - Single Line Text: Field Label: `Job Title`, Required: `ticked`, Placeholder: `Job Title`, Custom CSS Class: `gf_right_half`
  - Single Line Text: Field Label: `Email`,     Required: `ticked`, Placeholder: `Email`,     Custom CSS Class: `gf_left_half`
  - Single Line Text: Field Label: `Telephone`, Required: `ticked`, Placeholder: `Telephone`, Custom CSS Class: `gf_right_half`
- Select `Update Form` at the bottom of the right hand navigation to save changes
- Update the [Form Settings](#form-settings)

#### Form Settings

- Select `Form Settings` from  the navigation above the fields
- If necessary update the `Form title`
- Select `Confirmations` from the left hand navigation bar
  - Click on `Default Confirmation` to edit the confirmation page
  - Select Confirmation Type: `Page`
  - Select the Page previously setup: `Thank You - {{form name}}`
- Select `Notifications` from the left hand navigation bar
  - Click on `Admin Notification` to edit the notification
  - Update `Send to Email` to `info@obanmultilingual.com`
  - Update other fields according to the [conventions]() e.g.
    - From Name: `{Full Name:1}`
    - Reply To: `{Email:4}`
    - Subject: `[Oban Site GB] {form_title}`
  - Select `Update Notification` at the bottom of the page

#### Contact form conventions

Contact forms must have the:

- form name in the format
  ```
  ({{download}}) ({{type}}) {{name}}
  ```
  e.g.
  ```
  Download: Whitepaper 10 Key Dates
  Contact Us
  ```
- the from name set to the visitor's name:
  ```
  {Full Name:1}
  ```
- the from email set to:
  ```
  {admin_email}
  ```
- the reply to email set to the visitor's email:
  ```
  {Email:4}
  ```
- the subject in the form (note `{form_title}` will automatically pull in the name)
  ```
  [Oban Site {{2 letter iso code GB or US}}] {form_title}
  ```
  e.g.
  ```
  [Oban Site GB] {form_title}
  [Oban Site US] {form_title}
  ```

### Linking into a post

[Top](#oban-website-user-guide)

- Note the ID of the form you wish to display under the title
- Select `Posts` on the left hand navigation. This will display all posts.
- Locate the post you wish to add the form to
- Add the following html and shortcode to the page replacing the ID with the form id:

  ``` html
  <strong>Fill in the form below to receive your FREE whitepaper</strong>

  [gravityform id="{{id}}" title="false" description="false"]
  ```
- Click `Update` to save changes

### Creating a form page

[Top](#oban-website-user-guide)

- Select `Pages` from the left hand navigation.
- This will show a list of all the pages.
- Select `Add New` to create a new page
- Set the fields according to the [conventions](#form-page-conventions)
  - Parent in the right hand navigation to `Form`
  - Name to `Form - {{form name}}`
  - Body to (updating the name and link)

    ``` html
    [vc_row][vc_column width="1/1"][vc_column_text]
    <div id="infocal">
    <p style="text-align: center;">Thank you for your interest in our Global Partner Programme. Please fill in the form below and we will be in contact shortly.</p>

    </div>
    &nbsp;

    [/vc_column_text] [gravityform id=27 title=false description=false ajax=false tabindex=49][/vc_column][/vc_row]
    ```

  - All in One SEO Pack Title to a friendly title if required (overrides the name when viewing)
- Select Publish

#### Form page conventions

Thank you pages must have the:

- parent page set to
  ```
  Form
  ```
- title set to
  ```
  Form - {{form name}}
  ```
  e.g.
  ```
  Form - Download: Whitepaper 10 Key Dates
  ```
- Optionally: All in One SEO Pack title set to friendly text e.g.:
  ```
  Download your whitepaper.
  ```
