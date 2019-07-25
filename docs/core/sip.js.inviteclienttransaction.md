<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [sip.js](./sip.js.md) &gt; [InviteClientTransaction](./sip.js.inviteclienttransaction.md)

## InviteClientTransaction class

INVITE Client Transaction.

<b>Signature:</b>

```typescript
export declare class InviteClientTransaction extends ClientTransaction 
```

## Constructors

|  Constructor | Modifiers | Description |
|  --- | --- | --- |
|  [(constructor)(request, transport, user)](./sip.js.inviteclienttransaction._constructor_.md) |  | Constructor. Upon construction, the outgoing request's Via header is updated by calling <code>setViaHeader</code>. Then <code>toString</code> is called on the outgoing request and the message is sent via the transport. After construction the transaction will be in the "calling" state and the transaction id will equal the branch parameter set in the Via header of the outgoing request. https://tools.ietf.org/html/rfc3261\#section-17.1.1 |

## Properties

|  Property | Modifiers | Type | Description |
|  --- | --- | --- | --- |
|  [kind](./sip.js.inviteclienttransaction.kind.md) |  | <code>string</code> | Transaction kind. Deprecated. |

## Methods

|  Method | Modifiers | Description |
|  --- | --- | --- |
|  [ackResponse(ack)](./sip.js.inviteclienttransaction.ackresponse.md) |  | ACK a 2xx final response.<!-- -->The transaction includes the ACK only if the final response was not a 2xx response (the transaction will generate and send the ACK to the transport automagically). If the final response was a 2xx, the ACK is not considered part of the transaction (the transaction user needs to generate and send the ACK).<!-- -->This library is not strictly RFC compliant with regard to ACK handling for 2xx final responses. Specifically, retransmissions of ACKs to a 2xx final responses is handled by the transaction layer (instead of the UAC core). The "standard" approach is for the UAC core to receive all 2xx responses and manage sending ACK retransmissions to the transport directly. Herein the transaction layer manages sending ACKs to 2xx responses and any retransmissions of those ACKs as needed. |
|  [dispose()](./sip.js.inviteclienttransaction.dispose.md) |  | Destructor. |
|  [onTransportError(error)](./sip.js.inviteclienttransaction.ontransporterror.md) |  | The client transaction SHOULD inform the TU that a transport failure has occurred, and the client transaction SHOULD transition directly to the "Terminated" state. The TU will handle the failover mechanisms described in \[4\]. https://tools.ietf.org/html/rfc3261\#section-17.1.4 |
|  [receiveResponse(response)](./sip.js.inviteclienttransaction.receiveresponse.md) |  | Handler for incoming responses from the transport which match this transaction. |
|  [typeToString()](./sip.js.inviteclienttransaction.typetostring.md) |  | For logging. |

## Remarks

The INVITE transaction consists of a three-way handshake. The client transaction sends an INVITE, the server transaction sends responses, and the client transaction sends an ACK. https://tools.ietf.org/html/rfc3261\#section-17.1.1
