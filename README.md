## jQuery UI Dialog
```function show_dialog(message) {
    var $dialog = $('<div />');
    var o = function (tt) {
        $dialog.text(tt).dialog({
            autoOpen: true,
            show: "blind",
            hide: "fold",
            "resizable": false,
            //position: ['center', 'center'],
            position: { my: "center", at: "center", of: window },
            height: 90,
            minHeight: 90,
            create: function () {
                $(this).css("maxHeight", 90);
            },
            width: '260',
            modal: true,
            close: function () {
                $dialog.remove();
            }
        }).siblings('.ui-dialog-titlebar').remove();
    };
    var c = function () {
        $dialog.dialog('close');
        window.location.href = "../Home";
    };
    var magic = function () {
        o(message, 'x');
        setTimeout(function () {
            c('x');
        }, 3000);
    };
    magic();
}
```
