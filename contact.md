---
layout: default
title: Contact Nick
icon: fa fa-envelope-o
showtitle: true
permalink: /contact/
sitemap:
    priority: 0.7
    changefreq: monthly
    lastmod: 2013-10-22T14:31:44-05:00
---

<script src='https://www.google.com/recaptcha/api.js'></script>

<form action="https://formspree.io/contact2016@nickpadley.com"
      method="POST">
      <fieldset>
      <input type="hidden" name="_next" value="//www.nickpadley.com/contact/thanks/" />
      <input type="hidden" name="_subject" value="Contact Form Submission" />
      <input type="text" name="_gotcha" style="display:none" />
    <div class="form-group">
		<label for="name">Name</label>
		<input type="text" class="form-control" name="name" placeholder="Your Name" id="name" />
		</div>
	<div class="form-group">	
		<label for="email">Email</label>
    	<input type="email" name="_replyto" class="form-control" placeholder="email@domain.com">
    </div>
    <div class="form-group">	
		<label for="message">Message</label>
		<textarea class="form-control" rows="3" name="message" id="message"></textarea>
	</div>
    <button type="submit" class="btn btn-primary">Send</button>
    </fieldset>
</form>
