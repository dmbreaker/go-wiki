## This page has moved: https://golang.org/wiki/SendingMail ##
#labels smtp,package,example

# Sending Mail #

See also: http://golang.org/pkg/net/smtp/

Streaming the body:

```
package main

import (
        "bytes"
        "log"
        "net/smtp"
)

func main() {
        // Connect to the remote SMTP server.
        c, err := smtp.Dial("mail.example.com:25")
        if err != nil {
                log.Fatal(err)
        }
        // Set the sender and recipient.
        c.Mail("sender@example.org")
        c.Rcpt("recipient@example.net")
        // Send the email body.
        wc, err := c.Data()
        if err != nil {
                log.Fatal(err)
        }
        defer wc.Close()
        buf := bytes.NewBufferString("This is the email body.")
        if _, err = buf.WriteTo(wc); err != nil {
                log.Fatal(err)
        }
}
```

Authenticated SMTP:

```
package main

import (
	"log"
	"net/smtp"
)

func main() {
	// Set up authentication information.
	auth := smtp.PlainAuth(
		"",
		"user@example.com",
		"password",
		"mail.example.com",
	)
	// Connect to the server, authenticate, set the sender and recipient,
	// and send the email all in one step.
	err := smtp.SendMail(
		"mail.example.com:25",
		auth,
		"sender@example.org",
		[]string{"recipient@example.net"},
		[]byte("This is the email body."),
	)
	if err != nil {
		log.Fatal(err)
	}
}
```