
## Report: Suspicious Email Analysis

**From:** `Dr. Dan Miller`
**Email Address:** `babakingsouthmichael@gmail.com` 
**Reply-To:**  `imorourafiatou0@gmail.com`
**Brand Impersonated:** `Disaster Risk Reduction (UNDRR)`
**Originating IP:** `209[.]85[.]220[.]41`
**Domain of Interest:** `babakingsouthmichael[at]gmail[.]com`
**Shortened URL:** `none`
**Phishing Assessment:** `Likely Phishing`

---


This  detailed report regarding an email that has been identified as potentially suspicious or malicious. The email analysis is as follows:

1. **Email Timestamp**
   - Date and Time: `12:44 pm, Mar 3rd 2023`

2. **Email Details**
   - **From:** `Dr. Dan Miller`
   - **Sender's Email Address:** `babakingsouthmichael@gmail.com` 
   - **Reply-To Email Address:** `imorourafiatou0@gmail.com`

3. **Impersonated Brand**
   - The email was tailored to impersonate the brand: `Disaster Risk Reduction (UNDRR)`

4. **Originating IP**
   - The originating IP address is: `209[.]85[.]220[.]41`

5. **Domain of Interest**
   - The domain of interest is: `babakingsouthmichael[at]gmail[.]com`

6. **Shortened URL**
   - The email contains a shortened URL: `none`

7. **Phishing Assessment**
   - Based on the analysis conducted, it is my professional opinion that this email is likely a phishing email.
  
   A discrepancy between the 'To' and Received Lines is typically due to the email being sent to a Distribution List or the use of Blind Carbon Copy (BCC). This is a technique frequently used by spammers and attackers to send illegitimate and malicious emails to a large number of recipients.

Additional Information:
PhishTool used

```
Delivered-To: becode@phishing-me.be
Received: by 2002:a05:6a11:8598:b0:436:a25f:fe2 with SMTP id ci24csp543644pxc;
        Fri, 3 Mar 2023 03:44:03 -0800 (PST)
X-Received: by 2002:a0d:dfd8:0:b0:538:7870:f2da with SMTP id i207-20020a0ddfd8000000b005387870f2damr1233034ywe.1.1677843842978;
        Fri, 03 Mar 2023 03:44:02 -0800 (PST)
ARC-Seal: i=1; a=rsa-sha256; t=1677843842; cv=none;
        d=google.com; s=arc-20160816;
        b=v6L26mDP7HL7HgjNoFnZGfyLeuAPBYtfSO8rzQTBs85sEohMDMOr5uxRjf0ijWCnJj
         FBG2GS95+f4C/GKF/w1qGsD4f4nniYyhhhlgzFF7IhK1RsKhpWEfdL6I7NEJOttluHjc
         dWRhkDHHM/OrKiRhgyPScXMVxaxmu5t7IUs2tUikoD5Sw2s32XsPfBoBRo6zAQSbSvCc
         LBIuAGtzqQgHhUwqwfdDyYLZ0AttaXF2ZtgHt5AEmzfDxdwcRLAechyZ1pa7Bt0qU58m
         7YeAlUTEheplu1tTfv2AljPoQO1oH9TimEQVZsaVSwdo8uLCFCjzLZN+c8Bum2TDyF10
         Bc/Q==
ARC-Message-Signature: i=1; a=rsa-sha256; c=relaxed/relaxed; d=google.com; s=arc-20160816;
        h=content-transfer-encoding:to:subject:message-id:date:from:reply-to
         :mime-version:dkim-signature;
        bh=cQgP3aTREn7E1kjs8izwx03G1zP9+1Bw5n+Kswl0xwk=;
        b=jBalA2hiKO7nMaY/53PDvDZS5WV9VAdlRF5jNNancx9k+uELu9BLUv/bLLnzlLgC1k
         b722hxwOg4ZcUgL81FC2gPwwBfPNyW8lVBc3PDriIteTWxma4oUIV6nsLGB4FuzDVpIE
         eXUbdnX0VpLq8aBHvK+0gJ6pHG0hKdnlCkt8Lxs3I9xNDdti8iaya5V3OjTY7BKcB/+W
         KLSVqr+LeLdL5kRPZYDHWc20KmwkPrEAg+4xAJB4bqSnuo96Upo6V6nEHQgVYyEjMfaA
         mDlpoSt0EQnzl7XO81t8bu2shbonDK3WkRsyiCXISoiA74qmiZg4tKe0UrRCCIqBnmvU
         MQjg==
ARC-Authentication-Results: i=1; mx.google.com;
       dkim=pass header.i=@gmail.com header.s=20210112 header.b=alVDrquO;
       spf=pass (google.com: domain of babakingsouthmichael@gmail.com designates 209.85.220.41 as permitted sender) smtp.mailfrom=babakingsouthmichael@gmail.com;
       dmarc=pass (p=NONE sp=QUARANTINE dis=NONE) header.from=gmail.com
Return-Path: <babakingsouthmichael@gmail.com>
Received: from mail-sor-f41.google.com (mail-sor-f41.google.com. [209.85.220.41])
        by mx.google.com with SMTPS id q4-20020a0dec04000000b005384f5fda06sor1499668ywn.77.2023.03.03.03.44.02
        for <becode@phishing-me.be>
        (Google Transport Security);
        Fri, 03 Mar 2023 03:44:02 -0800 (PST)
Received-SPF: pass (google.com: domain of babakingsouthmichael@gmail.com designates 209.85.220.41 as permitted sender) client-ip=209.85.220.41;
Authentication-Results: mx.google.com;
       dkim=pass header.i=@gmail.com header.s=20210112 header.b=alVDrquO;
       spf=pass (google.com: domain of babakingsouthmichael@gmail.com designates 209.85.220.41 as permitted sender) smtp.mailfrom=babakingsouthmichael@gmail.com;
       dmarc=pass (p=NONE sp=QUARANTINE dis=NONE) header.from=gmail.com
DKIM-Signature: v=1; a=rsa-sha256; c=relaxed/relaxed;
        d=gmail.com; s=20210112; t=1677843842;
        h=content-transfer-encoding:to:subject:message-id:date:from:reply-to
         :mime-version:from:to:cc:subject:date:message-id:reply-to;
        bh=cQgP3aTREn7E1kjs8izwx03G1zP9+1Bw5n+Kswl0xwk=;
        b=alVDrquOs3714iWumyRf7tYU4Wifd9lb0FpHzwOHGkxoBS60qMKpq0seUv2ZdNfmdp
         HOohBCkSP0x+A0H8VkF3Ecy0BbPdWqUHolalq8N/sqaWLi4Gnb+4rnxjZ74xdXgSABVf
         IToW6GPd6Y0GV5gwHivazCLZO/s4Cci3t1rJN78xYMIbCpmeXGKb5IJBIxt38HZJXi0Y
         VWqhI47rhSj4QD8VttGUuIjr0BNsHEAO8MHDlGM9BU8KuxvbGJw6Xvcy80jAQjc7TY5j
         HC4XMJEtvq+hd9O6l4gj627/i93wgaqiOosxn04S4Ytmeb6AjIbPW/15xvMch4lxK7Z4
         GBBQ==
X-Google-DKIM-Signature: v=1; a=rsa-sha256; c=relaxed/relaxed;
        d=1e100.net; s=20210112; t=1677843842;
        h=content-transfer-encoding:to:subject:message-id:date:from:reply-to
         :mime-version:x-gm-message-state:from:to:cc:subject:date:message-id
         :reply-to;
        bh=cQgP3aTREn7E1kjs8izwx03G1zP9+1Bw5n+Kswl0xwk=;
        b=e6lzskKgQuxM2OBaXEbP5MuTBMCbBTw2LyG1dYtU1xqpRw7XBC/8R842upiobSUq4d
         IWZA+RCI5zyzZwKWTowvw74xeowvmbvaS90eGAHhPghWgE1PwiZO66Teub1h8Mxf8ADt
         oPm49UkSrpqjOe1RufXpt5gjNzbqb2JPccXSlTPmTosxxIBR39bwKLZRqzridnL0vkuk
         kq/PpXGF1eVyvPipnM0IiXjQwEZMVAkrYtZFVuG+jdLTw4R5sy8cPrl0xP3HJmqejNN4
         9bR1OT8wLReDhGTGsSq1z7wxFd6uXot2ud8jd5b00sDvxFMG1OM0SAgNP8A7pWd6cj6S
         afcw==
X-Gm-Message-State: AO0yUKXGiaWNPGyZuwglTAdOl89xUrlELrhLP9tZ27cySf4f8ry3PA5+ Vd8xCAtlYGy46u2n+ek2gfmMmPd8LmrC59vBtn8=
X-Google-Smtp-Source: AK7set8CUI3Dn7ZGnXp2R4Hbq+3ErtnsdM0XzdDhIufcxLWPR9A81VAA0N2YKtIcGVxtdV0tqvKk/KYoFsFcrPlXw5o=
X-Received: by 2002:a81:ae4a:0:b0:52e:b7cf:4cd1 with SMTP id g10-20020a81ae4a000000b0052eb7cf4cd1mr754691ywk.5.1677843842222; Fri, 03 Mar 2023 03:44:02 -0800 (PST)
MIME-Version: 1.0
Received: by 2002:a05:7000:b613:b0:480:c95c:35f6 with HTTP; Fri, 3 Mar 2023 03:44:01 -0800 (PST)
Reply-To: imorourafiatou0@gmail.com
From: "Dr. Dan Miller" <babakingsouthmichael@gmail.com>
Date: Fri, 3 Mar 2023 12:44:01 +0100
Message-ID: <CAELpv_2HOqRYMK6ZbFQpNZ+4iW=qi5pgm=5Le7QSVLcPx4Cy0w@mail.gmail.com>
Subject: Re: RELIEF / COMPENSATION FUND OF $1,500,000.00 USD
To: undisclosed-recipients:;
Content-Type: text/plain; charset="UTF-8"
Content-Transfer-Encoding: quoted-printable
Bcc: becode@phishing-me.be

Attn: Beneficiary,

I am  Dan Miller, the United Nations Special Representative for
Disaster Risk Reduction (UNDRR). We are pleased to inform you that
United Nations organization department for disaster management, in
conjunction with IMF, is giving out humanitarian relief fund worth the
total sum of $1,500,000.00 USD, and your E-mail Address has been
selected among other's to receive this humanitarian fund.

The United Nations Humanitarian Fund is a UN inter-agency fund
mechanism established by the UN Secretary-General to help support low
and middle income people(s) to respond to the humanitarian crisis,
including an unprecedented socio-economic shock. The Fund=E2=80=99s assista=
nce
programs targets those most vulnerable to economic hardship and social
disruption around the world.

We are delighted to inform you that due to mixed up of names and
numbers, your email which attached to approved number (UNHMC-198619),
which consequently fall on our Chapter, therefore, you are advised to
reach our grant manager ( Mr. Robert TAIWO ) at your earliest
convenient through his contact information's as stated below, to claim
your $1,500,000.00 USD relief support.

Name: Mr.  Robert TAIWO
Email Address:    (     mrroberttaiwo212@gmail.com    )
Telephone:  ( +229 ) 699 363 62

The information's required for the transfer of your Covid-19 Relief
fund, should include the following:

Given Name**
Residential/Office Address**
Phone Number**
Gender**

NOTE: that the amount to be paid to you is ( $1,500, 000.00 USD ), we
are expecting your urgent attention to this e-mail to enable us
monitor the transaction effectively.

Best Regards
Dan Miller.
Special Representative for Disaster Risk Reduction (UNDRR).
```