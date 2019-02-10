# Material Whoops
Material Dark Theme for [Laravel Whoops](https://github.com/filp/whoops) PrettyPageHandler

![Screenshot](https://github.com/CharlieEtienne/material-whoops/blob/master/screenshot.png)

## How to use

1. Create a folder in `app/public/vendor` named `whoops`

2. Create inside a folder named `css`

3. Paste [whoops-custom.css](https://github.com/CharlieEtienne/material-whoops/blob/master/whoops-custom.css) into `app/public/vendor/whoops/css`

4. Add the following into `app/Exceptions/Handler.php`

```php
  protected function whoopsHandler()
    {
        return tap(new PrettyPageHandler, function ($handler) {
            $directory = public_path().'\vendor\whoops';
            $css = '/css/whoops-custom.css';
            $handler->addResourcePath($directory);
            $handler->addCustomCss($css);
        });
    }
```

5. That's it
