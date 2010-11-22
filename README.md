Provdes an easy way to add Markdown to your symfony project.

Using the markdown and smartypants libraries from Michel Fortin, and the MarkItUp editor,
I have made an easy to use widget and library for using Markdown content in Symfony.

It assumes majaxJqueryPlugin is loaded (or some form of jQuery 1.4.x and jQuery UI 1.8.x)

* PHP Markdown: http://michelf.com/projects/php-markdown/
* PHP Smartypants: http://michelf.com/projects/php-smartypants/
* MarkItUp: http://markitup.jaysalvat.com/home/
* majaxJqueryPlugin: https://github.com/jmather/majaxJqueryPlugin

To use the widget in your Form class:

    class ... snip

      public function configure()
      {
        // ... snip ...

        $parameters = array();
        $attributes = array('style' => 'height: 100px;');
        $this->setWidget('content', new majaxWidgetFormMarkdownEditor($parameters, $attributes));

        // ... snip ...
      }
    }




To render the content:

      echo majaxMarkdown::transform($markdown_content);


You can control it with options in your app.yml:


    all:
      markdown:
        style: markdown_extra # choose markdown or markdown_extra
        smartypants_enabled: true # true / false
        smartypants_style: smartypants_typographer # choose smartypants or smartypants_typographer
        smartypants_options: 1 # You'll want to check the smartypants docs for more info on this...