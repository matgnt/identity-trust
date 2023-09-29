# DSP and SSI

Generally, SSI and VCs / VPs can be used to 'enrich naked identity' with VC based claims.

The often (often in technical systems communication) used 'client credentials' flow, does not use an */authorize* endpoint and thus, the general OID4VP flow (that is very human being centric) can not be applied directly.

With **client credentials** flow, the *authorization* is stored in the client's credentials it uses to authenticate itself at the authorization server.

Especially in a Dataspace, to manually register every client with every other dataspace partcipant's Authorization Server. A dynamic, automated registration, based on VCs each participant receives, is a scalable solution that still allows the use of well known OAuth *client credentials* flow.

**OAuth 2.0 Dynamic Client Registration Protocol**
https://datatracker.ietf.org/doc/html/rfc7591#section-3

As of now, there is no such dyanmic client registration starnadized that makes use of VCs.

## VC based dynamic client registration
![](auth.flow_with_registration.png)

After the client is registered, a regular access token to access a resource at another's participant resource can be fetched.
![](auth.flow_with_registration_token.png)

# DSP
Now the DSP protocol specific questions.

3rd party attested claims (VCs) that are supposed to be used beyond simple resrouce access control need to be handled differently.

Namely VCs required as part of a DSP contract negotiation process.

If VCs are required to proof fullfilling certain DSP contract policies, there are a few steps required:

- DSP needs to define how Policies / Rules can express such required proofs
- DSP shoud provide a mechanism to transfer the required proofs
- DSP needs to define errors in case those proofs are not accepted

The transfer of the proofs (VCs) may be defined as out-of-band. This is not the desired approach, but because of other constraints, it might be the intermediate solution.

![](auth.flow_dsp_contract_negotiation.png)
