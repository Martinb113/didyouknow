## Updates

### New Script Added
- **Become a Superhuman with Ask AT&T**: A 60-second impact script has been added under the 'Meet Ask AT&T' section in the `Start.md` file. This script introduces Ask AT&T as a powerful AI assistant that enhances productivity and creativity through effective prompt engineering. It includes an energetic opening, a superpower example, an explanation of prompt engineering, a reality check on AI's limitations, and a call to action to explore AI's potential.

This update aims to engage users by showcasing the transformative power of Ask AT&T in a concise and impactful manner. 

# Ask AT&T Email Campaign Instructions

This document provides step-by-step instructions for implementing the Ask AT&T email templates in a way that ensures compatibility with Outlook and other email clients.

## Outlook Compatibility Considerations

The HTML email templates have been designed with email client compatibility in mind, but Outlook has specific limitations:

1. **Rendering engine**: Outlook uses Microsoft Word's rendering engine which has limited CSS support
2. **Background images**: Might not display properly in some Outlook versions
3. **Border radius**: May appear as square corners in Outlook
4. **Box shadows**: Will be ignored in most Outlook versions
5. **Modern CSS**: Many modern CSS properties are not supported

## Step-by-Step Implementation Guide

### 1. Preparing Images

For reliable image rendering across all email clients:

```
a) Host all images on a reliable CDN or web server
   - Ensure the server is properly configured to serve images with correct MIME types
   - Use HTTPS URLs for all images
   - Avoid using relative paths

b) Image dimensions
   - Add explicit width and height attributes to all <img> tags
   - Resize images to their display size before uploading
   - Keep image file sizes under 200KB when possible

c) Image format recommendations
   - Use JPG for photographs
   - Use PNG for graphics with transparency
   - Consider using WebP with JPG fallbacks for modern clients
```

### 2. Adjusting Templates for Outlook

To ensure maximum compatibility with Outlook:

```
a) Replace background images
   - In the header section, consider using a solid color background (#0057b8) instead of the background image
   - Add the following VML code for Outlook compatibility where background images are used:

   <!--[if gte mso 9]>
   <v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" style="width:640px;">
   <v:fill type="tile" src="https://your-image-url.jpg" color="#0057b8" />
   <v:textbox style="mso-fit-shape-to-text:true" inset="0,0,0,0">
   <![endif]-->
   
   Content goes here
   
   <!--[if gte mso 9]>
   </v:textbox>
   </v:rect>
   <![endif]-->

b) Replace border-radius with Outlook-friendly alternatives
   - For rounded buttons, use:
   
   <!--[if mso]>
   <v:roundrect xmlns:v="urn:schemas-microsoft-com:vml" xmlns:w="urn:schemas-microsoft-com:office:word" href="#" style="height:45px;v-text-anchor:middle;width:280px;" arcsize="15%" stroke="f" fillcolor="#0057b8">
   <w:anchorlock/>
   <center style="color:#ffffff;font-family:sans-serif;font-size:16px;font-weight:bold;">BUTTON TEXT</center>
   </v:roundrect>
   <![endif]-->
   
   Then add a fallback for non-Outlook clients

c) Tables and spacing
   - Use cellpadding and cellspacing attributes on all tables
   - Avoid CSS padding in favor of table cell padding where possible
   - Use explicit width attributes on all table cells
```

### 3. Testing Process

Before sending to a mass audience:

```
a) Test with an email testing platform
   - Use platforms like Email on Acid or Litmus to preview in different clients
   - Pay special attention to Outlook 2007-2019 desktop versions

b) Send test emails to yourself
   - Send tests to Outlook accounts using different versions/devices
   - Check on both desktop and mobile Outlook apps

c) Check for these common issues:
   - Missing or broken images
   - Unexpected text wrapping
   - Misaligned content blocks
   - Font inconsistencies
   - Link functionality
```

### 4. Implementation in Email Service Providers (ESPs)

For proper deployment:

```
a) Mailchimp
   - Create a new campaign
   - Choose "Code your own" template option
   - Paste the entire HTML code
   - Replace image URLs with properly hosted ones
   - Test before sending

b) Constant Contact/Other ESP
   - Create a new custom email
   - Select "HTML Code" or similar option
   - Paste the HTML code
   - Verify tracking links work correctly
   - Test with the ESP's preview tools

c) Outlook 365 Admin
   - For organizational emails, work with your IT department
   - Ensure HTML emails are allowed for your organization
   - Consider creating an approved template in the admin center
```

### 5. Image Hosting Options

For reliable image delivery:

```
a) Email Service Provider hosting
   - Most ESPs offer image hosting
   - Upload images through their interface
   - Use their generated URLs in your HTML

b) Dedicated image hosting
   - Use services like Cloudinary or imgix
   - Set appropriate caching headers (Cache-Control: public, max-age=31536000)
   - Enable CORS if needed

c) Custom web hosting
   - Host on the same domain as your website when possible
   - Create a dedicated folder for email assets
   - Implement proper caching and compression
```

### 6. Troubleshooting Outlook-Specific Issues

If problems occur in Outlook:

```
a) Missing images
   - Verify images are properly hosted
   - Add explicit width/height attributes to all images
   - Add appropriate alt text

b) Layout breaks
   - Use tables for layout instead of divs
   - Add table layout="fixed" attribute 
   - Use width attributes on all TD elements

c) Fonts looking different
   - Stick to web-safe fonts (Arial, Times New Roman, etc.)
   - Provide adequate fallback fonts
   - Use inline font-family declarations

d) Links not working
   - Ensure all links have explicit https:// prefixes
   - Test all links after sending test emails
   - Avoid Javascript-based links
```

## Final Checklist Before Sending

- All images hosted on reliable servers with absolute URLs
- Outlook-specific code added for background images and rounded corners
- All tables have explicit widths and table cell spacing defined
- Font choices limited to email-safe options
- CTA buttons tested and working
- All links are absolute and working
- Test emails sent to various Outlook versions
- Preview text set properly
- Alt text added to all images

## Notes on Mobile Responsiveness

While these templates are designed to be responsive, note that:

1. Outlook mobile apps have better CSS support than desktop versions
2. Media queries may not work in all Outlook desktop versions
3. For best results on all devices, use a fluid layout with percentage-based widths

---

For further assistance or custom implementations, please contact the Ask AT&T email team. 