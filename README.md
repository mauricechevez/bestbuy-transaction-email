# Transactional Email - Best Buy
This is a recreation of a Receipt from Best Buy. My personal information has been redacted, and will be replaced with fictional info. The original email is **not** responsive. Although some responsiveness works in this version, I don't intend for it to be responsive either.

# Current Result
Email complete. I'm sure there's a programmatic way that the receipt section actually generates, but that's beyond the scope of this little project.
[https://mauricechevez.github.io/bestbuy-transaction-email/](https://mauricechevez.github.io/bestbuy-transaction-email/)

# Original Email Screenshot
This is the original email. Click the preview see the full image.

<a href="./img/email-screenshot.jpg" alt="Original Email"><img src="./img/email-screenshot_thumb.jpg" alt="original email"></a>

---
# Technlogies used
I decided to try an HTML Email Framework called [MJLM](https://mjml.io/). Although easier than Zurb's Foundation for Emails, so far I feel its limited compared to Foundation. I cannot find a way to run any javascript for easier templating, no SASS, and a lot of the sizing problems relate to padding. Its a lot of guess work on that front.
* MJML Framework
* HTML
* CSS

# MJML tags worth mentioning
### Social Media Icons
A nice feature from this framework is it includes social media icons that seem to be prevalent in marketing emails these days. The only issue is the included ones are plain, and might not match your template. Good thing is, you can use the same syntax that neatly adds these icons in an inline fashion, but add your own files (changing the src to your own assets). 
```mjml
<mj-column border-top="white 1px solid"> 
          <mj-social  align="left" color="#fff" padding-top="10px" icon-size="24px" >
             <mj-social-element href="https://www.facebook.com/bestbuy" src="img/facebook.gif">
             </mj-social-element>
              <mj-social-element href="https://www.twitter.com" src="img/twitter.gif">
             </mj-social-element>
             <mj-social-element href="https://www.instagram.com" src="img/instagram.gif">
             </mj-social-element>
             <mj-social-element href="https://www.pinterest.com" src="img/pinterest.gif">
             </mj-social-element>
             <mj-social-element href="https://www.linkedin.com" src="img/linkedin.gif">
             </mj-social-element>
          </mj-social>
    </mj-column>

```

# Important HTML tags
While making this email, I found a few HTML tags worth mentioning
1. `<pre>` - [Source](https://www.w3schools.com/tags/tag_pre.asp) This allowed me to create the receipt style font and styling in the email. The text displays exactly as typed. In other words, any spaces and line breaks you add will be displayed, like a Word doc, or typewriter. No need to add manual tags like `<br>`.
2. `<wbr>` -[Source](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr) Within the receipt, this tag allows the browser to break a word at time where normally it wouldn't break the word. This is good for long words which, if broken up in a different spot, would be harder to read. In this case, its the validation code which would break in the middle of the entire string, which makes sense.

# Resources
* [MJML Documentation](https://documentation.mjml.io/) - The documentation is good. Provides decent examples to start creating your own emails. I wish they would have given an actual example of how an external CSS file (or for that matter, an external MJML file) actually looks like besides a skeleton that doesn't display anything. I figured it out on my own after reading this [here](https://github.com/mjmlio/mjml/issues/1049).
* [Barcode Generator](https://www.cognex.com/resources/interactive-tools/free-barcode-generator) - Where I created a substitute barcode for this email. I manually cropped the one downloaded from here, as the original's height was short.