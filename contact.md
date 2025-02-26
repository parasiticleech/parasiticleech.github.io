---
layout: page
title: Contact
subtitle: Get in touch with Clyde Barker
---

# Contact Me

Have a question about a review? Want to suggest a product for me to review? Fill out the form below and I'll get back to you as soon as possible.

<div class="contact-form-container">
  <form id="contact-form">
    <div class="form-group">
      <label for="name">Name:</label>
      <input type="text" class="form-control" id="name" name="name" required>
    </div>
    
    <div class="form-group">
      <label for="email">Email:</label>
      <input type="email" class="form-control" id="email" name="email" required>
    </div>
    
    <div class="form-group">
      <label for="message">Message:</label>
      <textarea class="form-control" id="message" name="message" rows="5" required></textarea>
    </div>
    
    <button type="submit" class="btn btn-primary">Send Message</button>
  </form>
  
  <div id="success-message" style="display: none; margin-top: 20px;" class="alert alert-success">
    Thank you for your message! I'll get back to you as soon as possible.
  </div>
</div>

<script>
document.getElementById('contact-form').addEventListener('submit', function(event) {
  event.preventDefault();
  
  // Hide the form
  document.getElementById('contact-form').style.display = 'none';
  
  // Show success message
  document.getElementById('success-message').style.display = 'block';
  
  // In a real implementation, you would send the form data to a server here
  console.log('Form submitted');
});
</script>

<style>
.contact-form-container {
  max-width: 600px;
  margin: 0 auto;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}

.form-control {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.btn-primary {
  background-color: #0066cc;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
}

.btn-primary:hover {
  background-color: #0052a3;
}

.alert-success {
  background-color: #d4edda;
  color: #155724;
  padding: 15px;
  border-radius: 4px;
  border: 1px solid #c3e6cb;
}
</style>

## Other Ways to Reach Me

If you prefer not to use the contact form, you can also reach me through:

- **Email**: reviews@bestreviews.com
- **Twitter**: [@BestReviewsClyde](https://twitter.com/BestReviewsClyde)

I typically respond to all inquiries within 2 business days. 