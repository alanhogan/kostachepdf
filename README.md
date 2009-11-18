# PDF View

Extension for Kohana's View class that renders as a PDF instead of HTML. Uses [DOMPDF](http://code.google.com/p/dompdf/) to render normal HTML views as PDF Files.

**Please report all bugs related to PDF rendering to the [DOMPDF issue tracker](http://code.google.com/p/dompdf/issues/list).**

## Installation

If your application is a Git repository:

    git submodule add git://github.com/shadowhand/pdfview.git modules/pdfview
    git submodule update --init

Or clone the the module separately:

    cd modules
    git clone git://github.com/shadowhand/pdfview.git pdfview

Edit `application/bootstrap.php` and add a the module:

    Kohana::modules(array(
        ...
        'pdfview' => 'modules/pdfview',
        ...
    ));

## Usage

Placed in a controller action:

    // Load a view using the PDF extension
    $pdf = View_PDF::factory('pdf/example');
    
    // Use the PDF as the request response
    $this->request->response = $pdf;
    
    // Display the PDF in the browser as "my_pdf.pdf"
    // Remove "inline = TRUE" to force the PDF to be downloaded
    $this->request->send_file(TRUE, 'my_pdf.pdf', array('inline' => TRUE));

