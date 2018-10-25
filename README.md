# terraform-aws-guardduty-s3
[![CircleCI](https://circleci.com/gh/Mattias-/terraform-aws-guardduty-s3.svg?style=svg)](https://circleci.com/gh/Mattias-/terraform-aws-guardduty-s3)

This module writes [AWS GuardDuty](https://aws.amazon.com/guardduty/) findings to an AWS S3 bucket of your choice.
There will be one file per finding.

Usage:

```hcl
module "guardduty_s3" {
  source = "github.com/Mattias-/terraform-aws-guardduty-s3"
  bucket = "example"
}
```

Result:

```
$ aws s3 ls s3://example --recursive
2018-10-25 22:26:10       3029 2018/10/25/10b3562e61fab7a3a1135aa3c68b3644-guardduty.txt
2018-10-25 22:26:10       2016 2018/10/25/10b3562e61fc1e71f40483413db08369-guardduty.txt
2018-10-25 22:26:05       3001 2018/10/25/12b3562e61fb4e07174f4bb10463ec06-guardduty.txt
2018-10-25 22:26:10       1845 2018/10/25/12b3562e61fe51a0d28381230935c468-guardduty.txt
2018-10-25 22:26:09       2255 2018/10/25/1ab3562e62007073f745271c446d4976-guardduty.txt
2018-10-25 22:26:44       2984 2018/10/25/24b3562e62013e20efb720cf2d6fe836-guardduty.txt
2018-10-25 22:26:05       1868 2018/10/25/32b3562e61fa519f42316b01acba678d-guardduty.txt
2018-10-25 22:26:45       1683 2018/10/25/32b3562e61fb553edf497f0585a3c57a-guardduty.txt
2018-10-25 22:26:07       3486 2018/10/25/3cb3562e61f8cbfd9b9a0df251369a35-guardduty.txt
2018-10-25 22:26:44       3039 2018/10/25/48b3562e61fabfe8c976b3e67d36e4af-guardduty.txt
2018-10-25 22:26:07       1829 2018/10/25/5eb3562e61ff69b1c7b3cf8716c648c2-guardduty.txt
2018-10-25 22:26:44       3223 2018/10/25/60b3562e61fc0515e4f0cd9b2ab9b89c-guardduty.txt
2018-10-25 22:26:10       3488 2018/10/25/64b3562e61fa4a58d2096ce4ff9bb2f5-guardduty.txt
2018-10-25 22:26:10       3349 2018/10/25/6cb3562e61f9021034008ef00735da3e-guardduty.txt
2018-10-25 22:26:44       3464 2018/10/25/72b3562e61fda5241c43b20c8c56c363-guardduty.txt
2018-10-25 22:26:44       1686 2018/10/25/74b3562e61fe8b44ac7f9a6580b22011-guardduty.txt
2018-10-25 22:26:05       1836 2018/10/25/74b3562e6200f02bb69b5e68d008c69c-guardduty.txt
2018-10-25 22:26:10       1896 2018/10/25/7cb3562e6201e944c6f1b3299f02def0-guardduty.txt
2018-10-25 22:26:10       2457 2018/10/25/84b3562e61fcca982c523ba5647f9dda-guardduty.txt
2018-10-25 22:26:10       1864 2018/10/25/92b3562e61f940b6e90bbdd31fdc74ed-guardduty.txt
2018-10-25 22:26:07       2010 2018/10/25/96b3562e61fbd430d66f91e5a86008f3-guardduty.txt
2018-10-25 22:26:44       1977 2018/10/25/98b3562e61fe11106fdcfac380def0b8-guardduty.txt
2018-10-25 22:26:10       2982 2018/10/25/9ab3562e620115977e52461a75bebc76-guardduty.txt
2018-10-25 22:26:10       3025 2018/10/25/9cb3562e61fcb7d471799e3e7edaabdb-guardduty.txt
2018-10-25 22:26:44       2042 2018/10/25/b0b3562e61fd989d636866ebbff942f3-guardduty.txt
2018-10-25 22:26:07       3515 2018/10/25/b4b3562e61f889beb39c569b016875a7-guardduty.txt
2018-10-25 22:26:07       1943 2018/10/25/b4b3562e61fbc756a426357b7bf2b71c-guardduty.txt
2018-10-25 22:26:44       3010 2018/10/25/b4b3562e6200a74ea6b9edfc82ee3373-guardduty.txt
2018-10-25 22:26:10       3382 2018/10/25/b6b3562e61fd2d1c50dcc1104f00c489-guardduty.txt
2018-10-25 22:26:07       3461 2018/10/25/c0b3562e620100e1536dc6fca1811701-guardduty.txt
2018-10-25 22:26:44       3487 2018/10/25/c6b3562e61ff5e28e9156ed6ee9578ce-guardduty.txt
2018-10-25 22:26:10       3465 2018/10/25/c8b3562e61f9f27e0eb4a066117e7bf6-guardduty.txt
2018-10-25 22:26:06       2946 2018/10/25/c8b3562e6200183bb5a7c3cafaa3a152-guardduty.txt
2018-10-25 22:26:10       1915 2018/10/25/d6b3562e61fc7d61ec15103234007f15-guardduty.txt

```
