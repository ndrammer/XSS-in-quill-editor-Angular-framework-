# XSS-in-quill-editor-Angular-framework

In a recent pentest I was able to execute a XSS in an Angular quill rich text editor .

--------------------------

### Payload

```
<p><style>@keyframes x{}</style><strong style='animation-name:x' onanimationstart='alert(1)'></strong></p>
```

--------------------------

### PoC

Lunch quill editor  as a component in stackblitz.io platform and inject payload as shown in the image. 

![Angular XSS_quill-editor_full](https://github.com/user-attachments/assets/cae3de2e-4f28-4fac-becd-777f29609e4a)

Any other payloads are blocked, but not this one.

In a private pentest, attack was done in server side not just client side. The content of the message was inserted using a POST request using the description field, leading to a strored XSS.

![XSS-ServerSide](https://github.com/user-attachments/assets/4aa23821-b714-426b-81a1-37c575cd37bc)


This solution might be found in other implementations of quill editor.

--------------------------
### Google Bug Hunter comments

"We've decided that the issue you reported is not severe enough for us to track it as a security bug".
