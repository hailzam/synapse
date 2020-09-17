#To allow collection of email during registration and for password reset
#Below are the example configuration. Be aware that you can allow the email 
#to be optional or mandatory

#To make email mandatory during registration, enable the configuration below
#If this is not enabled, email will be optional during registration
registrations_require_3pid:
  - email


# The public-facing base URL that clients use to access this HS
# (not including _matrix/...). This is the same URL a user would
# enter into the 'custom HS URL' field on their client. If you
# use synapse with a reverse proxy, this should be the URL to reach
# synapse via the proxy.
#
public_baseurl: https://matrix.example.com

email:
  smtp_host: smtp.example.com

  # The port on the mail server for outgoing SMTP. Defaults to 25.
  #
  smtp_port: 2525

  # Username/password for authentication to the SMTP server. By default, no
  # authentication is attempted.
  #
  smtp_user: "your_smtp_username"
  smtp_pass: "your_smtp_password"
  
  # Uncomment the following to require TLS transport security for SMTP.
  # By default, Synapse will connect over plain text, and will then switch to
  # TLS via STARTTLS *if the SMTP server supports it*. If this option is set,
  # Synapse will refuse to connect unless the server supports STARTTLS.
  #
  require_transport_security: true

  # notif_from defines the "From" address to use when sending emails.
  # It must be set if email sending is enabled.
  #
  # The placeholder '%(app)s' will be replaced by the application name,
  # which is normally 'app_name' (below), but may be overridden by the
  # Matrix client application.
  #
  # Note that the placeholder must be written '%(app)s', including the
  # trailing 's'.
  #
  notif_from: "Your Friendly %(app)s homeserver <noreply@example.com>"
