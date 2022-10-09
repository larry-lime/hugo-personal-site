---
title: "Uba Content Best Practices"
date: 2022-10-09T19:49:56+08:00
draft: true
author: 0xLawrence
ShowToc: true
---

## Introduction
This article will be an overview of best practices to follow when publishing and managing content on my UBA's website

## News

#### Create a new newsletter post

1. Create a new hugo blog post
  ```shell
  hugo new blog/month-date.html
  ```

2. Copy and paste html code from MailChimp and paste it in the article

3. Format the HTML for consistency

   ```shell
   npx prettier FILE-NAME --write
   ```

4. Delete the following code blocks

   ```html
   <title>*|MC:SUBJECT|*</title>
   ```

   ```html
       <!--*|IF:MC_PREVIEW_TEXT|*-->
       <!--[if !gte mso 9]><!----><span
         class="mcnPreviewText"
         style="
           display: none;
           font-size: 0px;
           line-height: 0px;
           max-height: 0px;
           max-width: 0px;
           opacity: 0;
           overflow: hidden;
           visibility: hidden;
           mso-hide: all;
         "
         >*|MC_PREVIEW_TEXT|*</span
       ><!--<![endif]-->
       <!--*|END:IF|*-->
   ```

5. Replace the following words

   `Dear *|FNAME|*` -> `Dear UBA Members*`
