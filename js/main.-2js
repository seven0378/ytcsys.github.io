$(function () {
    Retrieve();
});

function Retrieve() {
    var dataArray = [];
    var script_url = 'https://script.google.com/macros/s/AKfycbxrryeM5iSl31VJGej49NI6NTwnL40ImEpXb7UNQdh6lvAG8wOjEALzEx60ROxvXHmz/exec';
    //var URL= script_url + "?action=ytcout";
    var URL = 'https://script.google.com/macros/s/AKfycbxrryeM5iSl31VJGej49NI6NTwnL40ImEpXb7UNQdh6lvAG8wOjEALzEx60ROxvXHmz/exec';
    $.ajax({
        url: URL,
        type: 'POST',
        dataType: "json",
        error: function (xhr) {
            alert('發生錯誤！請重新再試一次～');
        },
        success: function (Jdata) {
            var Info = Jdata.data;
            for (i = 0; Info.length > i; i++) {
                pdoName = Info[i].pdoName;
                pdate = Info[i].pdate;
                pcode = Info[i].pcode;
                pname = Info[i].pname;
                pnum = Info[i].pnum;
                pmemo = Info[i].pmemo;
                podd = Info[i].podd;
                poddnum = Info[i].poddnum;
                // 印出資料
                print();
            };

            //  資料列印
            function print() {
                $("#table-data").append(
                    '<tr>' +
                    '<td class="w-5">' + pdoName + '</td>' +
                    '<td class="w-8">' + pdate + '</td>' +
                    '<td class="w-10">' + pcode + '</td>' +
                    '<td class="w-20">' + pname + '</td>' +
                    '<td class="w-5">' + pnum + '</td>' +
                    '<td class="w-10">' + pmemo + '</td>' +
                    '<td class="w-10">' + podd + '</td>' +
                    '<td class="w-10">' + poddnum + '</td>' +
                    '</tr>'
                );
            };
            // 會議室搜尋            
            $("#doaction").click(function () {
                select();
            });

            function select() {
                var result = "";
                $("#select").each(function () {
                    var result = $(this).val();
                    //search_table($(this).val());
                    search_table2($(this).val(),0);
                });
            };

            function search_table(value) {
                $('tbody tr').each(function () {
                    var found = 'false';
                    $(this).each(function () {
                        if ($(this).text().toLowerCase().indexOf(value.toLowerCase()) >= 0) {
                            found = 'true';
                        }
                    });
                    if (found == 'true') {
                        $(this).show();
                    }
                    else {
                        $(this).hide();
                    }
                });
            }

            function search_table2(value, columnIndex) {
                $('tbody tr').each(function () {
                  var found = 'false';
                  var columnValue = $(this).find('td').eq(columnIndex).text();
                  if (columnValue.toLowerCase().indexOf(value.toLowerCase()) >= 0) {
                    found = 'true';
                  }
                  if (found == 'true') {
                    $(this).show();
                  } else {
                    $(this).hide();
                  }
                });
              }
            
        }
    });
};



