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

   ```html
         <tr>
        <td align="center" valign="top" style="padding-top: 20px; padding-bottom: 20px">
          <table border="0" cellpadding="0" cellspacing="0" id="canspamBar">
            <tr>
              <td align="center" valign="top" style="
                    color: #606060;
                    font-family: Helvetica, Arial, sans-serif;
                    font-size: 11px;
                    line-height: 150%;
                    padding-right: 20px;
                    padding-bottom: 5px;
                    padding-left: 20px;
                    text-align: center;
                  ">
                This email was sent to
                <a href="mailto:*|EMAIL|*" target="_blank" style="color: #404040 !important">*|EMAIL|*</a>
                <br />
                <a href="*|ABOUT_LIST|*" target="_blank" style="color: #404040 !important"><em>why did I get
                    this?</em></a>&nbsp;&nbsp;&nbsp;&nbsp;<a href="*|UNSUB|*"
                  style="color: #404040 !important">unsubscribe from this list</a>&nbsp;&nbsp;&nbsp;&nbsp;<a
                  href="*|UPDATE_PROFILE|*" style="color: #404040 !important">update subscription preferences</a>
                <br />
                *|LIST:ADDRESSLINE|*
                <br />
                <br />
                *|REWARDS|*
              </td>
            </tr>
          </table>
        </td>
      </tr>
   ```

   ```html
    <tbody>
      <tr>
        <td
          valign="top"
          class="mcnTextContent"
          style="
            padding-top: 0;
            padding-right: 18px;
            padding-bottom: 9px;
            padding-left: 18px;
            mso-line-height-rule: exactly;
            -ms-text-size-adjust: 100%;
            -webkit-text-size-adjust: 100%;
            word-break: break-word;
            color: #ffffff;
            font-family: Helvetica;
            font-size: 12px;
            line-height: 150%;
            text-align: center;
          "
        >
          <em
            >Copyright © 2022 Undergraduate
            Business Association at New York
            University Shanghai, All rights
            reserved.</em
          >
        </td>
      </tr>
    </tbody>
   ```

5. Replace the following words

   `Dear *|FNAME|*` -> `Dear UBA Members*`

6. Add the first paragraph of the email to the `Summary` front-matter
