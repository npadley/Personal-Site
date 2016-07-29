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

<form action="https://getsimpleform.com/messages?form_api_token=6b1927e2fed1206550614981db4aad06" method="post">
	<fieldset>
	  <input type='hidden' name='redirect_to' value='https://www.nickpadley.com/contact/thanks/' />
		<div class="form-group">
			<label for="name">Name</label>
			<input type="text" class="form-control" name="name" placeholder="name" id="name" />
		</div>
		<div class="form-group">	
			<label for="email">Email</label>
			<input type="email" class="form-control" name="email" placeholder="email" id="email" />
		</div>
		<div class="form-group">	
			<label for="message">Message</label>
			<textarea class="form-control" rows="3" name="message" id="message"></textarea>
		</div>
		<div class="form-group">
			<div class="g-recaptcha" data-sitekey="6LeTVSYTAAAAAEl9x_oMBxYa_1SmzkB8UiWZYMuH"></div>
		</div>
		
		<button type="submit" class="btn btn-primary">Submit</button>
  </fieldset>
</form>