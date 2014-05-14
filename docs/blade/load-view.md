# @Blade to Excel

We can utilise the magic of Laravel's Blade engine to power our Excel export. Sharing a view, loading a view per sheet, creating a html table inside a view, basic CSS styling, ...

# Loading a view for a single sheet

We can load a view for every sheet we create with `->loadView()`.

    Excel::create('New file', function($excel) {

        $excel->sheet('New sheet', function($sheet) {

            $sheet->loadView('folder.view');

        });

    });

# Sharing a view for all sheets

We can share a view for all sheets with `shareView()`

    Excel::shareView('folder.view')->create();

# Unsetting a view for a sheet

When we are using a the share view, but we don't want to use a view for the current sheet, we can use `->unsetView()`

    $sheet->unsetView();