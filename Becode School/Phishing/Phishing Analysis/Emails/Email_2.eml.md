
## Report: Suspicious Email Analysis

**From:** `stainless@midnightmagicevents.com`
**Email Address:** `stainless@midnightmagicevents.com`
**Reply-To:** `stainless@midnightmagicevents.com`
**Brand Impersonated:** `Trust Wallet`
**Originating IP:** `85[.]209[.]134[.]107`
**Domain of Interest:** `stainless[at]midnightmagicevents[.]com`
**Shortened URL:** `hxxps[;//]climovil[.]com/`
**Phishing Assessment:** `Likely Phishing`

---


This  detailed report regarding an email that has been identified as potentially suspicious or malicious. The email analysis is as follows:

1. **Email Timestamp**
   - Date and Time: `09:56 am, Dec 12th 2022`

2. **Email Details**
   - **From:** `stainless@midnightmagicevents.com`
   - **Sender's Email Address:** `stainless@midnightmagicevents.com`
   - **Reply-To Email Address:** `stainless@midnightmagicevents.com`

3. **Impersonated Brand**
   - The email was tailored to impersonate the brand: `Trust Wallet`

4. **Originating IP**
   - The originating IP address is: `85[.]209[.]134[.]107`

5. **Domain of Interest**
   - The domain of interest is: `stainless[at]midnightmagicevents[.]com`

6. **Shortened URL**
   - The email contains a shortened URL: `hxxps[;//]climovil[.]com/`

7. **Phishing Assessment**
   - Based on the analysis conducted, it is my professional opinion that this email is likely a phishing email
  
   The verification links contains a malicious virus that most will collect information form the device that clicks on the link and the link forwards to a  unrelated website what is very suspicious:

```
Webroot: [malicious](https://www.virustotal.com/gui/search/entity%253Aurl%2520webroot%253A%2522malicious%2522)
```
   

Additional Information:
I used the PhishTool platform to find all the information I needed for this task


```
Received: from MW6PR19MB6903.namprd19.prod.outlook.com (::1) by
 MN0PR19MB6312.namprd19.prod.outlook.com with HTTPS; Wed, 14 Dec 2022 05:54:16
 +0000
Received: from DM6PR06CA0019.namprd06.prod.outlook.com (2603:10b6:5:120::32)
 by MW6PR19MB6903.namprd19.prod.outlook.com (2603:10b6:303:238::5) with
 Microsoft SMTP Server (version=TLS1_2,
 cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id 15.20.5880.10; Wed, 14 Dec
 2022 05:54:14 +0000
Received: from DM6NAM11FT101.eop-nam11.prod.protection.outlook.com
 (2603:10b6:5:120:cafe::90) by DM6PR06CA0019.outlook.office365.com
 (2603:10b6:5:120::32) with Microsoft SMTP Server (version=TLS1_2,
 cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id 15.20.5880.19 via Frontend
 Transport; Wed, 14 Dec 2022 05:54:14 +0000
Authentication-Results: spf=none (sender IP is 172.81.119.154)
 smtp.mailfrom=midnightmagicevents.com; dkim=pass (signature was verified)
 header.d=midnightmagicevents.com;dmarc=bestguesspass action=none
 header.from=midnightmagicevents.com;compauth=pass reason=109
Received-SPF: None (protection.outlook.com: midnightmagicevents.com does not
 designate permitted sender hosts)
Received: from vps37336.servconfig.com (172.81.119.154) by
 DM6NAM11FT101.mail.protection.outlook.com (10.13.172.208) with Microsoft SMTP
 Server (version=TLS1_2, cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id
 15.20.5924.10 via Frontend Transport; Wed, 14 Dec 2022 05:54:14 +0000
X-IncomingTopHeaderMarker:
 OriginalChecksum:E18E8F871A468425DE2CE8E0AB9DEB62EF77CF18F1EA31AB8E7CFCF3A5A9E228;UpperCasedChecksum:6224925CE711C0618C66200DF7454D9D3BF8B5D84E04ACAF19F2664D1D073DCD;SizeAsReceived:2002;Count:19
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
	d=midnightmagicevents.com; s=default; h=Message-ID:Date:
	Content-Transfer-Encoding:Content-Type:Subject:To:Reply-To:From:MIME-Version:
	Sender:Cc:Content-ID:Content-Description:Resent-Date:Resent-From:
	Resent-Sender:Resent-To:Resent-Cc:Resent-Message-ID:In-Reply-To:References:
	List-Id:List-Help:List-Unsubscribe:List-Subscribe:List-Post:List-Owner:
	List-Archive; bh=1rRUNHDZt/ySaBaZbYBU3hfIx64gbZbNAP9oYSHytI8=; b=pZXgHeI0zrP8
	/oOKSHD0XtASxp9wg9MHUySE1yHncLXBgr8KIR3gd2BIk8JTk4Mual+A9Pk3HAMyOOo/JqgOG6L3h
	jGotZi6T5p0Lcayp2wFw1h+wv3x/0Qnubm0+TNLZ1hDXYVVqrC5qltlKKgAZzhmwFhnXtOPdfb8H8
	tJ9gFgxK9y5xmO2531AoB+l986DQhYaHj08tZ8yb81V47MfSGWkW/Qn9VcoC9HJp+8EIc0ingPNR/
	4hZ1ZX8S0VoZrN9oVtkgTXsO0nxuz32F65NsY2/SqbnAhrFK2Bk+lm5FOm1DRbh96ZzHjFVXRPbey
	Z2v8sPz7Fz/Xw1+ky/DwDg==;
Received: from [85.209.134.107] (port=52623 helo=85.209.134.107)
	by vps37336.servconfig.com with esmtpa (Exim 4.95)
	(envelope-from <stainless@midnightmagicevents.com>)
	id 1p4ec1-0002EZ-L0
	for phishing@pot;
	Mon, 12 Dec 2022 03:56:38 -0500
From: "noreply" <stainless@midnightmagicevents.com>
Reply-To: stainless@midnightmagicevents.com
To: phishing@pot
Subject: Trust Wallet
Content-Type: text/html; charset="windows-1252"
Content-Transfer-Encoding: quoted-printable
X-Mailer: Smart_Send_3_1_6
Date: Mon, 12 Dec 2022 09:56:36 +0100
Message-ID: <5348421712496313174540@WIN-HM6FI4VOIEP>
X-AntiAbuse: This header was added to track abuse, please include it with any abuse report
X-AntiAbuse: Primary Hostname - vps37336.servconfig.com
X-AntiAbuse: Original Domain - hotmail.com
X-AntiAbuse: Originator/Caller UID/GID - [47 12] / [47 12]
X-AntiAbuse: Sender Address Domain - midnightmagicevents.com
X-Get-Message-Sender-Via: vps37336.servconfig.com: authenticated_id: stainless@midnightmagicevents.com
X-Authenticated-Sender: vps37336.servconfig.com: stainless@midnightmagicevents.com
X-IncomingHeaderCount: 19
Return-Path: stainless@midnightmagicevents.com
X-MS-Exchange-Organization-ExpirationStartTime: 14 Dec 2022 05:54:14.6083
 (UTC)
X-MS-Exchange-Organization-ExpirationStartTimeReason: OriginalSubmit
X-MS-Exchange-Organization-ExpirationInterval: 1:00:00:00.0000000
X-MS-Exchange-Organization-ExpirationIntervalReason: OriginalSubmit
X-MS-Exchange-Organization-Network-Message-Id:
 26a53a9e-560c-4e58-5c14-08dadd97a186
X-EOPAttributedMessage: 0
X-EOPTenantAttributedMessage: 84df9e7f-e9f6-40af-b435-aaaaaaaaaaaa:0
X-MS-Exchange-Organization-MessageDirectionality: Incoming
X-MS-PublicTrafficType: Email
X-MS-TrafficTypeDiagnostic: DM6NAM11FT101:EE_|MW6PR19MB6903:EE_
X-MS-Exchange-Organization-AuthSource:
 DM6NAM11FT101.eop-nam11.prod.protection.outlook.com
X-MS-Exchange-Organization-AuthAs: Anonymous
X-MS-UserLastLogonTime: 12/13/2022 10:17:00 PM
X-MS-Office365-Filtering-Correlation-Id: 26a53a9e-560c-4e58-5c14-08dadd97a186
X-MS-Exchange-EOPDirect: true
X-Sender-IP: 172.81.119.154
X-SID-PRA: STAINLESS@MIDNIGHTMAGICEVENTS.COM
X-SID-Result: PASS
X-MS-Exchange-Organization-PCL: 2
X-MS-Exchange-Organization-SCL: 6
X-Microsoft-Antispam: BCL:0;
X-MS-Exchange-CrossTenant-OriginalArrivalTime: 14 Dec 2022 05:54:14.5458
 (UTC)
X-MS-Exchange-CrossTenant-Network-Message-Id: 26a53a9e-560c-4e58-5c14-08dadd97a186
X-MS-Exchange-CrossTenant-Id: 84df9e7f-e9f6-40af-b435-aaaaaaaaaaaa
X-MS-Exchange-CrossTenant-AuthSource:
 DM6NAM11FT101.eop-nam11.prod.protection.outlook.com
X-MS-Exchange-CrossTenant-AuthAs: Anonymous
X-MS-Exchange-CrossTenant-FromEntityHeader: Internet
X-MS-Exchange-CrossTenant-RMS-PersistedConsumerOrg:
 00000000-0000-0000-0000-000000000000
X-MS-Exchange-Transport-CrossTenantHeadersStamped: MW6PR19MB6903
X-MS-Exchange-Transport-EndToEndLatency: 00:00:01.8834076
X-MS-Exchange-Processed-By-BccFoldering: 15.20.5880.019
X-Microsoft-Antispam-Mailbox-Delivery:
	abwl:0;wl:0;pcwl:0;kl:0;dwl:0;dkl:0;rwl:0;ucf:0;jmr:0;ex:0;auth:1;dest:J;OFR:SpamFilterAuthJ;ENG:(5062000305)(90000117)(90005022)(91005020)(91035115)(5061607266)(5061608174)(9050020)(9100338)(2008001134)(2008121020)(4810004)(4910033)(8820095)(9710001)(9610025)(9535003)(10155021)(9320005)(9245025);RF:JunkEmail;
X-Message-Info:
	6hMotsjLow9GFc5Bau/fbw0r+Sh/9N0E9zRuKxjP4xOAd31CX1l11B+9NajYckcVC37wj80ixw7815Hfs5S4etnQSCLc8BCwSP1LQeyliJlScOvxa9PAOptBTUeC/7rAeiIitB1Eu9vU1r2pEoCYPVFyeLNi9Qr39TM6fAXvSE6V5ZUfq1AH5DAcIjhRElPzWMIAFj4GhyH38s4zJ5CuJA==
X-Message-Delivery: Vj0xLjE7dXM9MDtsPTA7YT0wO0Q9MjtHRD0zO1NDTD02
X-Microsoft-Antispam-Message-Info:
	=?Windows-1252?Q?/w/LBJupEqt572w92+kf0jJXWBs8DJXbMW28d34pi9Ce8Wa8E3rdE/Nv?=
 =?Windows-1252?Q?qCYyE3I8L26qzqe9SUGXAhsiLetDAtZqSDrStpGnLOFHtV1rgAZO7LvM?=
 =?Windows-1252?Q?CTaoSBs8mIWaf2gScbTa5CKBtVCNbwqGyBuaUfCbjjFc+gFoHB5pPxB0?=
 =?Windows-1252?Q?e5pQR0QvXiYzywVsb8XYyspflj0JlrJ9TJPgX4UsO+cEeHRNarq/mEb2?=
 =?Windows-1252?Q?O0r0mx1AEgQYbETG/FdI4U5s3PKzOs3tDqCwOQojR7c5vRQIY/ML/F5e?=
 =?Windows-1252?Q?bQpPeDkzQmoecM5YR2RNQwvF+klIybv9izyqi+rev8uokSk58/0kVOBE?=
 =?Windows-1252?Q?MgmEe8I1JUgtJ7w0bZqD0VVN7U8vgfNWd32UnFAxJMfpZBNM5IatcraL?=
 =?Windows-1252?Q?ZQ4xsYrL8oyJnDogy+rUghso9syzL/j4I1fMX3CKTiUI+W28wEEgWyBC?=
 =?Windows-1252?Q?jO1cZ3dB7sRicsL+ZUhSYU9IKaKNi6qGrAjrU5VYoPksSv7+UvyZPVQW?=
 =?Windows-1252?Q?7jSruS5gEojss9GsKZzwD14gvJoz0/oMcfUFDv7LtRqzhKuU0rS1a7k8?=
 =?Windows-1252?Q?pp7pecX1Cbp7IhQ8r0IGkTWBsqVmFvQDwMv9v6JCxXOmtTGDxPs6yb0T?=
 =?Windows-1252?Q?pSdeRd74sA0/ZscHYcrCxBuRgZLZspekGopykhQ7MUCFll6lWugKF0oW?=
 =?Windows-1252?Q?l/XOrI26YeYEAeIFEfDtBnaKk7g8BHjqDR3slYWzbcG9hd7ajt3UGkHo?=
 =?Windows-1252?Q?Ovo4kXC+s1v5GaqX07MYfTbVMxswCe5GQ6i5YPaLhbOCGwwPJu1kgMZ3?=
 =?Windows-1252?Q?XNOBZFGNiBjxFvowQDDIuA93IGCzLmIwEYfjUrEQli3YGCEFUZ5vh+vT?=
 =?Windows-1252?Q?Te4zltvOuqVGB6yklPDnFoXRFGTZuzIW82kDlsfzKHBJCD+0I/OPGuPd?=
 =?Windows-1252?Q?ypZseaSbV8CpQDOXVOKY45PttQWHZbuublNx6BmiOAvpGn/aV512WqaL?=
 =?Windows-1252?Q?BxwVNlr6hOxrTowxyWDRx+qax0YWmwxh3ptQs2iUzupnwhTaGYKa6Sh4?=
 =?Windows-1252?Q?12QK/Aaii09JVFynXPURYtZosLuCuJW1JKzcsAADq8Lv21UJX03LowAt?=
 =?Windows-1252?Q?QnIr6gb5Z0UqSt4mYfIsRP5zQQjKeMPivu3ZeQNasvMBjC3yYE6ViZmZ?=
 =?Windows-1252?Q?Tkr9dUyEVXybKDU2zCFYtTMdgrrugy5zW1Us8PFX6oz/1+KyL9azXtu3?=
 =?Windows-1252?Q?348+/aQ+zSp05JFUtu7lOgEia9+aXR6c4ScaQ4X2wP/Gr/YnVP3CZiH9?=
 =?Windows-1252?Q?FJDFug28qgPArllkIR0Y92a5SviuFkp07CMOk0ahKkJtMgPWVV4Sr74I?=
 =?Windows-1252?Q?sM6lGXtfYA+ggxzDhCmJ6xDqRoXSwV8DgwjQvtYYbOc/OLUCq/ghPEaN?=
 =?Windows-1252?Q?Rs1lP9EwDgsH3vGI2IHlIYB608E0jvV8h/nc0MVdlNkgUweVketeDMuS?=
 =?Windows-1252?Q?GeGqLGrJOj6oUAIk2Qkqw4UCHxo9gcJtN7UYS+bp50kFVKb5eZ297Ds1?=
 =?Windows-1252?Q?b36mQX19gsDxVXDA35+u9y4Te5t1WvZg1wxpM/ezL9OLgLF5TgmDemXo?=
 =?Windows-1252?Q?2UBBrJSIbL+snScAyHzX//vjH4+ZagDR/0kzfppRXGn7J+jmVoDT2SLk?=
 =?Windows-1252?Q?l+ZTx43aORnUYv7t4RQ0HrP6Pv2nz+M/WIv00FXOeCSdV7WvDAv7ZSfU?=
 =?Windows-1252?Q?94egRdWY98kyptRrcwxqSn+kk2TK7cyHV4UYhATKUpYXRnC5b6/BIPPo?=
 =?Windows-1252?Q?OdPML6Z0y15C4hGr3rRX3VTbGOdNDG6cv9O0uEeIwukrx+XKNClsvJGP?=
 =?Windows-1252?Q?qpiXHpoxNlrC1wOXCSC1olQL3RS10Lxyq+t78ZR30lJLZAWiLs2gubqU?=
 =?Windows-1252?Q?v+MPYzKMDAxUoeCSis745YqkvGuqlllITjLVAjGJb/HmgHN3VzFqexUB?=
 =?Windows-1252?Q?+e6zZyG0rNIN3CHsenKpAOpHfClJiIbSPYn7lDrmVcF6nP87Ko81m3yS?=
 =?Windows-1252?Q?orkWbY4RyzvDPaaSE1yjQuUcvvGH2IgxKtLBpjevI2PJleOzIXJHxe70?=
 =?Windows-1252?Q?WZSUGbwBY5zwkyXGqoMxFIBdhWB3VXSnYumHPFbrFlfGvxN85pYRVKYm?=
 =?Windows-1252?Q?O9bHteZuxN0mcOI5qhiKvQyMJlu4JQ3HkgX+dnC6wSyB9KXM0KmCoK+l?=
 =?Windows-1252?Q?7YgSPTbaUu86NNyf5J3yh8TrkwAeZWyAhnrnR0t0Ti5n96p3/rbpz3jA?=
 =?Windows-1252?Q?KDdVE5/+Hq5zpo302TH/f/5U/1TT5wkTvNplHWWTtMgVvjLVss1rKL1Z?=
 =?Windows-1252?Q?ZrehQ6I6Fq3AI7F+4hH314LdEpufovS1wx/aRnVl1PdIL9mFE93zmTy1?=
 =?Windows-1252?Q?arcQS3eNRtP0v8tZLzOXx7N5JTT+9KrvZ95PXcljTDqiNxtr5K1q88yn?=
 =?Windows-1252?Q?74MQ1B4Ym+39fmNYQdoTjjsZA0P3RmPWpaL4yVGB6vujR7rJ2Ms8ba64?=
 =?Windows-1252?Q?qZrGT3/OelkSCZ0NKrOxvgu53Wf+HZO2Nto6SLTPP5eA5iH8qZbxR6T/?=
 =?Windows-1252?Q?lQmbdfBh/4xZ8in4vTogX/fznCeetlJ5rcGFoW3bg4h2jSRUh+PO0dgW?=
 =?Windows-1252?Q?+hcQGIvdNAPq/JEqZ6jQz+7q6lqquiq3FkO2ACKPoNijz2gMA5IGHaQB?=
 =?Windows-1252?Q?BPveJ6oExNH6sCLmj/SOhwasXi9ipfCYaypY7WkI6maN9l0wqUjdFa/L?=
 =?Windows-1252?Q?Ow0AGQm1+IhiaY0g5Swi5m6GnG8zLw6yRDjWw0ne6jX4AWPvPwh7XlFX?=
 =?Windows-1252?Q?szyJiB2GPHXkEmWgSoLzzuuJA7k2N1x6KOJ1rnN3P0kUH2j9M/dDozpA?=
 =?Windows-1252?Q?dgJBUydA/kHNJy765/HAYSvPRI27bp1iNTYwO1pvVrJ/vsx/zAD6Z/uT?=
 =?Windows-1252?Q?JYNPGQp1?=
MIME-Version: 1.0

<head>
<meta http-equiv=3D"Content-Type" content=3D"text/html; charset=3DWindows-1=
252">
<meta name=3D"GENERATOR" content=3D"MSHTML 11.00.10570.1001"></head>
<body>
<p><font size=3D"2"><img style=3D"BORDER-TOP: 0px; HEIGHT: 152px; BORDER-RI=
GHT: 0px; WIDTH: 312px; VERTICAL-ALIGN: baseline; BORDER-BOTTOM: 0px; COLOR=
: ; PADDING-BOTTOM: 0px; PADDING-TOP: 0px; PADDING-LEFT: 0px; BORDER-LEFT: =
0px; MARGIN: 0px; PADDING-RIGHT: 0px" alt=3D"Best Cryptocurrency Wallet | E=
thereum Wallet | ERC20 Wallet | Trust Wallet" src=3D"https://trustwallet.co=
m/assets/images/media/preview/horizontal_blue.png" width=3D"498" height=3D"=
250" data-imagetype=3D"External"></font></p>
<p><font size=3D"3">Dear Customer</font></p>
<p><font size=3D"3">Our system has shown that your&nbsp;Trust Wallet&nbsp;h=
as not yet been verified, this verification can be done on the page below.<=
/font></p>
<p><font size=3D"3">Due to the recently update of NFT's &amp; Coins, all un=
verified accounts will be suspended.</font></p>
<p><font size=3D"3"></font>&nbsp;</p>
<p>
<table role=3D"presentation" style=3D"FONT-SIZE: 13px; FONT-FAMILY: Roboto,=
 RobotoDraft, Helvetica, Arial, sans-serif; WIDTH: 178px; WHITE-SPACE: norm=
al; WORD-SPACING: 0px; BORDER-COLLAPSE: separate !important; TEXT-TRANSFORM=
: none; FONT-WEIGHT: 400; COLOR: rgb(29,34,40); FONT-STYLE: normal; MIN-HEI=
GHT: 39px; BORDER-SPACING: 0px !important; ORPHANS: 2; WIDOWS: 2; LETTER-SP=
ACING: normal; BACKGROUND-COLOR: rgb(255,255,255); font-variant-ligatures: =
normal; font-variant-caps: normal; text-decoration-style: initial; text-dec=
oration-color: initial; font-variant-numeric: inherit; font-variant-east-as=
ian: inherit; font-stretch: inherit" cellspacing=3D"0" cellpadding=3D"0" al=
ign=3D"left" border=3D"0">
<tr>
<td style=3D"FONT-SIZE: 14px; FONT-FAMILY: Arial, sans-serif; WHITE-SPACE: =
normal !important; BORDER-COLLAPSE: collapse; WORD-BREAK: normal; COLOR: rg=
b(18,18,18); BACKGROUND-COLOR: rgb(25,127,196); border-radius: 8px" bgcolor=
=3D"#197fc4" valign=3D"middle" align=3D"center"><a style=3D"FONT-SIZE: 16px=
; TEXT-DECORATION: none; BORDER-TOP: 0px; FONT-FAMILY: arial, helvetica, sa=
ns-serif; BORDER-RIGHT: 0px; VERTICAL-ALIGN: baseline; BORDER-BOTTOM: 0px; =
TEXT-TRANSFORM: none; COLOR: rgb(0,164,189); PADDING-BOTTOM: 12px; PADDING-=
TOP: 12px; PADDING-LEFT: 18px; BORDER-LEFT: 0px; MARGIN: 0px; DISPLAY: bloc=
k; PADDING-RIGHT: 18px; font-stretch: inherit" href=3D"https://climovil.com=
/" rel=3D"nofollow noopener noreferrer" target=3D"_blank" data-linkindex=3D=
"0" data-auth=3D"NotApplicable"><strong style=3D"TEXT-DECORATION: none; FON=
T-WEIGHT: normal; COLOR: rgb(255,255,255); FONT-STYLE: normal">Go to verifi=
cation</strong></a></td></tr></table></p>
<p><font size=3D"3"></font>&nbsp;</p>
<p>&nbsp;</p>
<p><font size=3D"3">For further assistance with this issue, please contact =
our support team.</font></p></body>
```