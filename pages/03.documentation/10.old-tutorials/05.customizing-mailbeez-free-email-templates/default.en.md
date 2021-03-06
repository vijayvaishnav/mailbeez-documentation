---
# http://learn.getgrav.org/content/headers
title: Customizing MailBeez Free Email Templates
slug: customizing-mailbeez-free-email-templates
# menu: Customizing MailBeez Free Email Templates
date: 11-07-2012
published: true
publish_date: 11-07-2012
# unpublish_date: 11-07-2012
template: docs
# theme: false
visible: true
summary:
    enabled: true
    format: short
    size: 128
taxonomy:
    migration_status: review
    category: [docs]
    tag: []
# added collection selector

author:
    name: kelly
metadata:
    author: kelly
#      description: Your page description goes here
#      keywords: HTML, CSS, XML, JavaScript
#      robots: noindex, nofollow
#      og:
#          title: The Rock
#          type: video.movie
#          url: http://www.imdb.com/title/tt0117500/
#          image: http://ia.media-imdb.com/images/rock.jpg
#  cache_enable: false
#  last_modified: true
---

The screenshots used in this tutorial were made using Zen Cart. If you use a different e-commerce platform, your admin interface and MailBeez interface may appear slightly different, however the concepts and configuration instructions are the same across all platforms.

## About This Tutorial

This tutorial will guide you through the MailBeez free email template system step-by-step, providing you with the knowledge to customize your MailBeez generated emails so that you can create powerful & effective marketing campaigns for your e-commerce business that are also attractive to your customers!

In this tutorial, we will discuss:

- Before You Begin Customizing
- Working With Email Templates
- Understanding Email Template Structure
- Creating Your Own Custom Templates
- Backing Up Your Customizations
- How To: Popular Global Template Customizations
- How To: Popular Individual Module Template Customizations
- Additional Tips for Zen Cart Users

## Before You Begin Customizing

Before you begin customizing your free email templates, you **must create a backup of the original templates** that came pre-installed with the free email modules so you can restore the templates if you break something during customization.

Once you complete your customizations, **it is strongly recommended** that you make back up copies for later use in the event that you update your email modules. If you are using Template Manager or Multilanguage Extension with Template Manager, this is a **must**.

Step-by-step instructions can be found in later sections of this tutorial.

## Working With Email Templates

The MailBeez email template system is structured to use global templates as well as sub-templates which are specific to each MailBeez module. Some of the customizations you make will be on a global scale whilst others are made on a per-module basis.

### Global Template Changes

Which changes are best made globally? Any customizations you make to the Common Main Template are shared among all MailBeez modules, so you will want to limit these customizations to those you wish to see in all emails that MailBeez generates.

Here are some examples:

- Custom email header image
- Custom header and/or footer text and/or links
- Ensure customer name is always capitalized
- Your email closing or signature

### Individual Module Changes

Which changes are best made on a per module basis? Any customization that you wish to apply to the emails generated by a specific module should be made on a per module basis by editing the module’s sub-templates. For example:

- Custom text to reflect the nature and style of your store
- Custom images for each module
- Change the date format in those modules that use a date to reflect how dates are expressed in your country
- Custom layout to reflect your taste and preferred styling

### Customize in 3 Easy Steps

- Send yourself two test emails, one in HTML and one in TXT format to preview the default templates & determine what types of customizations you’d like to make
- Make your changes by editing the template files as instructed in the customization sections of this tutorial
- Test your changes by using the “View Mail” and “Send Test Email” functionality built into each MailBeez email module

## Understanding Email Template Structure

Mailbeez emails are 100% template based, and therefore can be customized without any programming knowledge whatsoever. As long as you are comfortable with a little HTML editing, you will be able to make changes to Mailbeez templates or even create your own.

Visually, the template hierarchy of the MailBeez free email template system looks like this:

Common Main Template  
 This content is global and will apply to all emails generated by MailBeez Module specific Body Template  
 This content is specific to each module and will apply only to emails generated by its module

 

Looking at it this way, it is easy to see that module specific content generated by module sub-templates is tucked nicely inside the email framework generated by the Common Main Template.

### Common Main Templates

The Common Main Templates are global templates, meaning that their contents are shared among all MailBeez modules. There are 2 of them; 1 to generate email in HTML format and 1 to generate email in TXT format. They are located here:

(shop-root)/mailhive/common/templates/**email\_html.tpl** (HTML version)

(shop-root)/mailhive/common/templates/**email\_txt.tpl** (TXT version)

### Sub-Templates

The sub-templates are individual templates which are unique to each module. The content of a sub-template file is merged into the Common Mail Template file, bringing global data like the email header image together with specific module data, such as the birthday greeting text which is unique to the Birthday Greeting module, to create one nicely integrated email.

All free email modules have at least 3 templates; 1 to generate email in HTML format, 1 to generate email in TXT format, and 1 to generate the subject line. (Some modules, like the Review Simple & Share Review on Facebook modules have additional templates to generate product list content). Sub-templates are located here:

(shop-root)/mailhive/mailbeez/(module)/email/**subject.tpl**

(shop-root)/mailhive/mailbeez/(module)/email/**body\_html.tpl** (HTML version)

(shop-root)/mailhive/mailbeez/(module)/email/**body\_txt.tpl** (TXT version)

## Creating Custom Templates

**Do not skip this step! Creating custom templates is a necessary step to avoid losing your customizations when you update your MailBeez framework and modules or when using Template Manager module to restore your original templates!**

With MailBeez free email modules, you may create one set of custom individual module templates per module and one set of custom global templates. Since MailBeez free email modules all rely on their default file names to function correctly, the way to accomplish the creation of custom templates is to create re-named back-ups of the original files before making any customizations, while leaving the file names “as is” for the templates you customize.

The end result of this process is that you are able to fully customize all of your templates to suit your needs, while retaining a back up of the original in case you break your template and need to restore the original or update your MailBeez framework or email modules to recent versions as they are released. Step-by-step instructions follow.

### Custom Global Templates

Remembering that global templates and the Common Main templates are in fact one and the same, just follow these few simple steps:


- In your Mailbeez fileset on your local drive, navigate to: /mailhive/common/templates/email\_html.tpl

[![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/lib/scripts/timthumb/thumb.php?src=http://www.mailbeez.com/images/doc/premium_email_tut/common_main_template.png&w=270&h=92&zc=1&q=100 "Common Main Email Templates")](http://www.mailbeez.com/images/doc/premium_email_tut/common_main_template.png "Common Main Email Templates")![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/images/shortcodes/image_shadow.png)


- Open the file in a text editor and then save it with a new name: perhaps email\_html\_original.tpl
- Repeat this process with the TXT template:  /mailhive/common/templates/email\_txt.tpl

[![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/lib/scripts/timthumb/thumb.php?src=http://www.mailbeez.com/images/doc/premium_email_tut/common_main_template_backup.png&w=270&h=93&zc=1&q=100 "Custom Common Main Email Templates")](http://www.mailbeez.com/images/doc/premium_email_tut/common_main_template_backup.png "Custom Common Main Email Templates")![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/images/shortcodes/image_shadow.png)

That’s it! You have just created your first set of Custom Global templates by doing nothing more than creating back up copies of the original files! You may now safely edit your Custom Global templates without worrying about data loss next time you upgrade MailBeez or use Template Manager’s template restore function.

Just remember to keep a copy of both your original and customized files on your local drive.

What if you’ve already customized the original template files? No problem! Just follow the steps above using the files from your original download package or, if you no longer have it, download it again from [the download section](http://www.mailbeez.com/download/)

If you are creating multilingual emails with the Multilanguage Extension with Template Manager module, there is no need to create Custom Global templates for each language – the module will do it for you! See the “Using the Multilanguage Template Manager With Free Email Templates” section of the [Multilanguage Extension with Template Manager tutorial](/documentation/tutorials/multilanguage-extension-with-template-manager-configuration-tutorial/)

### Custom Individual Module Templates

Using the Birthday Greetings module as an example, just follow these few simple steps:


- In your Mailbeez fileset on your local drive, navigate to: /mailhive/mailbeez/birthday/email/body\_html.tpl

[![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/lib/scripts/timthumb/thumb.php?src=http://www.mailbeez.com/images/doc/premium_email_tut/birthday_templates.png&w=270&h=107&zc=1&q=100 "Birthday Greetings Email Templates")](http://www.mailbeez.com/images/doc/premium_email_tut/birthday_templates.png "Birthday Greetings Email Templates")![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/images/shortcodes/image_shadow.png)


- Open the file in a text editor and then save it with a new name: perhaps body\_html\_**original**.tpl
- Repeat this process with the TXT template: /mailhive/mailbeez/birthday/email/body\_txt.tpl

[![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/lib/scripts/timthumb/thumb.php?src=http://www.mailbeez.com/images/doc/premium_email_tut/birthday_templates_backup.png&w=270&h=103&zc=1&q=100 "Birthday Greetings Custom Email Templates")](http://www.mailbeez.com/images/doc/premium_email_tut/birthday_templates_backup.png "Birthday Greetings Custom Email Templates")![](http://localhost/wordpress_mailbeez_EOL/wp-content/themes/awake/images/shortcodes/image_shadow.png)

That’s it! You have just created your first set of Custom individual module templates by doing nothing more than creating back up copies of the original files! You may now safely edit your Custom templates without worrying about data loss next time you upgrade MailBeez or use Template Manager’s template restore function.

Since the files for all of the MailBeez email modules are organized in the same way, you can easily repeat these steps for each free module by simply navigating to the template files for each module:

/mailhive/mailbeez/MODULE\_NAME/email/body\_html.tpl

Just remember to keep a copy of both your original and customized files on your local drive.

What if you’ve already customized the original template files? No problem! Just follow the steps above using the files from your original download package or, if you no longer have it, download it again from [the download section](http://www.mailbeez.com/download/)

If you are creating multilingual emails with the Multilanguage Extension with Template Manager module, there is no need to create Custom individual module templates for each language – the module will do it for you! See the “Using the Multilanguage Template Manager With Free Email Templates” section of the [Multilanguage Extension with Template Manager tutorial](/documentation/tutorials/multilanguage-extension-with-template-manager-configuration-tutorial/)

## Backing Up Your Customizations

Once you have completed your customizations, it is crucial that you keep a copy of the customized template (.tpl) files on your local drive. Because the custom file names are the same as the default file names, when you update your MailBeez framework and email modules as new versions are released, you could easily overwrite your customizations without thinking.

Keeping a back up copy ensures you will be able to easily restore your customizations if you mistakenly overwrite them during a software update.

### Template Manager Users

If you are using either the Template Manager or Multilanguage Extension with Template Manager modules to customize your templates, the process for backing up your changes is more involved than just keeping a copy of the file on your hard drive. Please see the “Backing Up Your Customizations” section of the Template Manager tutorial for the module you are using:

- [Template Manager](/documentation/tutorials/template-manager/)
- [Multilanguage Extension with Template Manager](/documentation/tutorials/multilanguage-extension-with-template-manager-configuration-tutorial/)

## Global Template Customizations

Global customizations result from changes made to a single template file, yet they affect all of the emails MailBeez sends out, regardless of the module being used. This makes customizing your MailBeez email templates a quick and easy process so you can get up and running right away!

**To make a customization global, make your edits to the Common Main Template, found at catalog/mailhive/common/templates/email\_html.tpl.**

To get you started, here are instructions for some of the more popular customizations:

### Change the Email Header Image

Changing out the email header image is as easy as can be! Just follow these simple steps:

- Create a new image with a width of 600px
- Name the new image. For example “mynewheader.png”
- Using your preferred FTP program, upload the new image to “catalog/mailhive/common/images/”
- Edit the Common Main Template as indicated below
- Find the line of code which defines the email header image: ![](<strong>{$catalog_server}mailhive/common/images/default_emailheader.gif</strong>)
- Edit the code shown above to reflect the new image name to get this: ![]({$catalog_server}mailhive/common/images/<strong>mynewheader.png</strong>)

### Edit the Header and/or Footer

Navigate to catalog/mailhive/common/templates/email\_html.tpl and edit it with your preferred text editor. Yes, it’s that easy!

If you would like to have the MailBeez Copyright Notice removed from the free email templates, you may do so by either upgrading the free module to the premium version, or by purchasing the [MailBeez Copyright Remover Certificate](/documentation/configbeez/config_copyright_remover/)

### Capitalize the Customer Name

Sometimes customers use lower case when entering their information to create an account. If you want to make sure customer names are formatted properly, regardless of how the customer entered their data, you can apply this modifier by adding this:

|capitalize:true

To this:

{$firstname} {$lastname}

To get this:

{$firstname|capitalize:true} {$lastname|capitalize:true}

Which will generate capitalized output in emails:

Joe Smith

**[More information about modifiers](http://www.smarty.net/docsv2/en/language.modifiers.tpl#language.modifier.capitalize)**

## Individual Module Customizations

Each MailBeez module comes with its own set of customizable template files (sub-templates) which are used to generate the email in both HTML and TXT formats. Individual module customizations result from changes made to a module’s email template files, and only affect the emails sent out by that particular module.

This provides you with the flexibility to customize emails on a per module basis without worrying that your changes will appear in every email MailBeez generates.

To customize a module’s email templates, simply make your edits to that module’s email templates. You will remember from the section on Sub-Templates that they are found here:

(shop-root)/mailhive/(module)/email/**subject.tpl**

(shop-root)/mailhive/(module)/email/**body\_html.tp**l (html version)

(shop-root)/mailhive/(module)/email/**body\_txt.tpl** (txt version)

To get you started, here are instructions for some of the more popular customizations:

### Changing Text

Using the Birthday Greeting module and the HTML template as an example, let’s say you want to change the closing of the email:

- Navigate to catalog/mailhive/mailbeez/birthday/email/body\_html.tpl
- Locate the block of text containing the closing: **yours**{$storename} {$storeurl}
- Change it to something you prefer, for example “Sincerely,” to get this: **Sincerely,**{$storename} {$storeurl}

### Changing Images

Changing out the email images are just as easy as changing the header image! Using the Birthday Greeting module as an example, let’s say you want to change the default birthday cake image to an image of balloons & confetti. Just follow these simple steps:

- Create a new image, sized 256px by 256px
- Name the new image. For example “balloons.png”
- Using your preferred FTP program, upload the new image to  ”catalog/mailhive/mailbeez/birthday/images/”
- Edit the Birthday Greeting email template (catalog/mailhive/mailbeez/birthday/email/body\_html.tpl) as indicated below
- Find the line of code which defines the Birthday Greeting image: ![](<strong>{$catalog_server}mailhive/mailbeez/birthday/images/birthday_cake.png</strong>)
- Edit the code shown above to reflect the new image name to get this: ![]({$catalog_server}mailhive/mailbeez/birthday/images/<strong>balloons.png</strong>)

If you decide to use an image which is sized differently than the default image (256×256), then you will need to also edit the “width” and “height” parameters in the code above to match the new image size. Depending on how you size the image, you may also need to edit the “align” parameter and/or move the image to a new position within the layout.

### Changing the Layout

Changing the layout of your email module templates is as simple as moving various elements, or blocks of code, from one place to another within the template. If you move an image, you will have to take the extra step of changing the “align” parameter to match it’s new location, depending on where you place it.

Once again, let’s use the Birthday Greeting module as an example. Let’s say you want to replace the default image with a banner image named “bdbanner.png”, sized to a width of 600px and a height of 150px and have it center across the top of the email. Let’s also say that you want to move the customer’s first name to be after the “Happy Birthday” text, and you want to eliminate the last name altogether.

Here’s how:

- Follow the above instructions on changing an image, except as noted below.
- Change the image source code to reflect the new image parameters as follows: ![]({$catalog_server}mailhive/mailbeez/birthday/images/<strong>bdbanner.png</strong>)
- Move the new image source code to the place you want it to appear in the template. In this case, above the Happy Birthday message, changing this: Happy Birthday!![]({$catalog_server}mailhive/mailbeez/birthday/images/<strong>bdbanner.png</strong>)

to this:

![]({$catalog_server}mailhive/mailbeez/birthday/images/<strong>bdbanner.png</strong>)Happy Birthday!
- Next, move the code that generates the customer’s first name so it is positioned between “Happy Birthday” and “!”, and then delete the code that generates the customer’s last name. “Happy Birthday!” becomes “Happy Birthday firstname: {$firstname}!”. If your customer’s first name is Sarah, the generated output will be “Happy Birthday Sara!”

### Change the Date Format

Variable modifiers allow you to adjust the output format of a date to your needs. For example, adding this:

|date\_format:”%A, %B %e, %Y”

To this:

{$date\_of\_birth}

Gives you this:

{$date\_of\_birth|date\_format:”%A, %B %e, %Y”}

Which will generate date output that looks like this in the Birthday Greeting email:

Saturday, December 1, 1984

**[More Info on Date Related Modifications](http://www.smarty.net/docsv2/en/language.modifier.date.format.tpl)**

## Additional Tips for Zen Cart Users

### General Tips

- Make sure Zen Cart is configured to send email in HTML format. The Zen Cart tutorial for this is located here: http://tutorials.zen-cart.com/index.php?article=113
- For running simulations, make sure you have a test customer account set up in your Zen Cart and that it is configured to receive email in HTML format and that the configured email address for the test account is capable of rendering email in HTML format
- For sending test email, make sure you send one test to an account capable of rendering email in HTML format, and one test to an account that is configured to receive in TXT format. This way, you can see how both HTML and TXT formatted emails will appear to your customers.
- The best email services for rendering HTML based email are web-based email like gmail, hotmail, etc. Hosting account email services are generally configured to block HTML to protect the server.

### Using Zen Cart’s Template System

In MailBeez v2.6 and above, you can opt to use your Zen Cart email template system instead of using the MailBeez email template system. While it is recommended to use the MailBeez email template system due to ease of customization & use, you can certainly opt not to.

If you choose to use the Zen Cart email template system, or are running a MailBeez version prior to v2.6 which requires you to use the Zen Cart email template system, then an additional layer is added to the template hierarchy:

Zen Cart Default Email Template  
 This content is generated by Zen Cart’s email\_template\_default.html file and will apply to all emails Common Main Template  
 This content is global and will apply to all emails generated by MailBeez Module specific Body Template  
 This content is specific to each module and will apply only to emails generated by its module

 

 

Looking at it this way, it is easy to see the impact your Zen Cart default email template has on the content generated by the MailBeez template system and why careful editing & extensive testing will be necessary. Zen Cart’s default email template is located here: (shop-root)/emails/email\_template\_default.html



## Make Customization Even Easier

Customizing MailBeez email templates is fairly easy to begin with. All it takes is a **little** knowledge of basic HTML and some testing. But if you want to make it even easier, MailBeez offers a variety of ways to accomplish this:

- [Template Manager](/documentation/configbeez/config_tmplmngr/) – Edit email templates right from the admin!
- [Add Gender](/documentation/filterbeez/filter_add_gender/) – Customize email based on gender!
- [Extended Customer Information](/documentation/filterbeez/filter_add_customer_information/) – Personalized customer emails!
- [MailBeez Professional Services](http://www.mailbeez.com/support/service/) – Hire a MailBeez Pro to do it for you!
- [Upgrade Your Free Email Modules](http://www.mailbeez.com/download/) – Premium email modules come with a variety of professionally designed templates!
