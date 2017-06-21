# mPDF wrapper for laravel inspired by [laravel-dompdf](https://github.com/barryvdh/laravel-dompdf)

Require this package in your composer.json and update composer.
```
composer require praem90/laravel-mpdf
```

## Installation
### Laravel 5.x
After updating composer, add the ServiceProvider to the providers array in config/app.php

    Praem90\PDF\ServiceProvider::class,

You can optionally use the facade for shorter code. Add this to your facades:

    'PDF' => Praem90\PDF\Facade::class,

## Using

Use 'PDF' Facade to interact with mPdf object

```
    $pdf = PDF::loadView('pdf.invoice', $data); // or PDF::loadHtml($html);
    return $pdf->download($filename); // or
    return $pdf->stream($filename);
```
You can access all the available mPDF methods directly by the same facade.
eg.,
```
    $pdf->setColumns(2);
    $pdf->loadView($blade_path1, $data1); // or $pdf->loadHtml($html) or $pdf->WriteHTML('html)
    $pdf->addColumn();
    $pdf->loadView($blade_path2, $data2);
``` 
