# script editor template 

### メール通知
```
/* 問い合わせがきたことを管理者アドレスにメール通知する */
function sendMailToAdmin(e){
  
  var adminmail = 'hoge@hoge.com;'  /* 問い合わせがあったことを通知したいEmailアドレスを指定する */
  var items = e.response.getItemResponses();
  var subject = "Get message from Googleform"
  var body = '';
  var msg = '';
  
  for (var i = 0; i < items.length; i++) {
    var item = items[i];
    var q = item.getItem().getTitle();
    var a = item.getResponse();
    
    msg += '[' + q + ']：' + a + '\n';
  }
  
  body = "You recives message from the Google form!\n\n" + msg
  
  GmailApp.sendEmail(adminmail, subject, body);
}
```

```
/* 問い合わせ者に自動返信する */
function autoReply(e) {
        
  var items = e.response.getItemResponses();
  var subject = "Thanks for contacting azusaw!";
  var body = '';
  var msg = '';
      
  for (var i = 0; i < items.length; i++) {
    var item = items[i];
    var q = item.getItem().getTitle();
    var a = item.getResponse();
    
    if (q == 'name') var name = a;
    
    if (q == 'email') var usermail = a;
    
    msg += q + ': ' + a + '\n';
  }
  
  body = "Dear "
  + name
  + '\n\n'
  + 'Thank you for your message.'
  + '\n'
  + 'I will check and reply as soon as possible.\n\n'
  + '--- Your Message ---\n'
  + msg
  
  GmailApp.sendEmail(usermail, subject, body);
}
```
