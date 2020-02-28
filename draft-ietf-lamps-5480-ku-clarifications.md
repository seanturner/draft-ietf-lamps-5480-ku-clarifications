---
title:  Clarifications for Elliptic Curve Cryptogtaphy Subject Public Key Information
abbrev: Clarifications for ECC SPKI
docname: draft-ietf-lamps-5480-ku-clarifications-latest
date: {DATE}
category: std
updates: 5480

ipr: trust200902
area: Security
workgroup: LAMPS
keyword: Internet-Draft

stand_alone: yes
pi: [toc, sortrefs, symrefs]

author:
 -
    ins: T. Ito
    name: Tadahiko Ito
    organization: SECOM CO., LTD.
    email: tadahiko.ito.public@gmail.com
 -
    ins: S. Turner
    name: Sean Turner
    organization: sn3rd
    email: sean@sn3rd.com

normative:

informative:

--- abstract

This document updates RFC 5480 to specify semantics for the keyEncipherment
and dataEncipherment key usage bits when used in certificates that support Elliptic
Curve Cryptography.

--- middle

Introduction
=

{{!RFC5480}} specifies the syntax and semantics for the Subject Public Key
Information field in certificates that support Elliptic Curve Cryptography.  As part
of these semantics, it defines what combinations are permissible for the values
of the key usage extensions {{!RFC5280}}.  {{RFC5480}} specifies  7 of the 9
values; it makes no mention of keyEncipherment and dataEncipherment key
usage bits.  This document corrects this omission, by updating Section 3
of {{RFC5480}} to make it clear that neither keyEncipherment nor the
dataEncipherment key usage bits are set for key agreement algorithms
defined therein.  The additions are to be made to the end of Section 3.

Terminology
=

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they appear in
all capitals, as shown here.

Updates to Section 3
=

If the keyUsage extension is present in a certificate that indicates id-ecPublicKey in SubjectPublicKeyInfo, then following values MUST NOT be present:

~~~
  keyEncipherment; and
  dataEncipherment.
~~~~

If the keyUsage extension is present in a certificate that indicates id-ecDH or id-ecMQV in SubjectPublicKeyInfo, then the following values also MUST NOT be present:

~~~
  keyEncipherment; and
  dataEncipherment.
~~~

Security Considerations
=

This document introduces no new security considerations beyond those found in
{{RFC5480}}.

IANA Considerations
=

This document makes no request of IANA.

--- back
