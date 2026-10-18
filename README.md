
# twilio-java

This [SDK](https://github.com/sdk-fabric/twilio-java) is managed by the [SDK Fabric](https://sdk-fabric.org/) project, a global infrastructure to
automatically generate SDKs for every API.

You can find more information about this SDK at [TypeHub](https://typehub.cloud/):
https://app.typehub.cloud/d/sdkfabric/twilio

## Usage

```java
import org.sdkfabric.twilio.Client;

Client client = Client::build("[access_token]");

// Delete the Media resource.
Object response = client.media().delete("accountSid", "messageSid", "sid");

// Fetch a single Media resource associated with a specific Message resource.
Media response = client.media().get("accountSid", "messageSid", "sid");

// Read a list of Media resources associated with a specific Message resource.
Media_Collection response = client.media().getAll("DateCreated", 1, 1, "PageToken", "accountSid", "messageSid");

// Send a message (SMS, MMS, WhatsApp or other channel).
Message response = client.messages().create("accountSid", new Object());

// Deletes a Message resource from your account.
Object response = client.messages().delete("accountSid", "sid");

// Fetch a specific Message.
Message response = client.messages().get("accountSid", "sid");

// Retrieve a list of Message resources associated with a Twilio Account.
Message_Collection response = client.messages().getAll("DateSent", "From", 1, 1, "PageToken", "To", "accountSid");

// Update a Message resource (used to redact Message `body` text and to cancel not-yet-sent messages).
Message response = client.messages().update("accountSid", "sid", new Object());
```
