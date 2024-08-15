---
layout: page
title: Contact
---

If you would like to reach me by email please fill out and submit the form below. I am usually able to reply to your email within a few hours.

<form
  id="contactForm2"
  action="https://formspree.io/f/mzzpgkgo"
  method="POST"
  style="display: flex; flex-direction: column; max-width: 500px; margin: auto; padding: 20px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); backdrop-filter: blur(10px); transition: all 0.3s ease; background: rgba(255, 255, 255, 0.8); animation: fadeIn 1s ease-in-out;"
  onsubmit="handleFormSubmit2(event)"
>
  <label
    style="margin-bottom: 15px; font-weight: bold; color: #333; animation: slideIn 1s ease-out;"
  >
    Your email:
    <input
      type="email"
      name="email"
      required
      style="width: 100%; padding: 10px; margin-top: 5px; border: 1px solid #ddd; border-radius: 4px; transition: border-color 0.3s ease, box-shadow 0.3s ease;"
      onfocus="this.style.borderColor='#007bff'; this.style.boxShadow='0 0 5px rgba(0, 123, 255, 0.5)';"
      onblur="this.style.borderColor='#ddd'; this.style.boxShadow='none';"
    >
  </label>
  <label
    style="margin-bottom: 15px; font-weight: bold; color: #333; animation: slideIn 1.2s ease-out;"
  >
    Your message:
    <textarea
      name="message"
      required
      style="width: 100%; padding: 10px; margin-top: 5px; border: 1px solid #ddd; border-radius: 4px; transition: border-color 0.3s ease, box-shadow 0.3s ease;"
      onfocus="this.style.borderColor='#007bff'; this.style.boxShadow='0 0 5px rgba(0, 123, 255, 0.5)';"
      onblur="this.style.borderColor='#ddd'; this.style.boxShadow='none';"
    ></textarea>
  </label>
  <button
    type="submit"
    style="padding: 10px 20px; border: none; border-radius: 4px; background-color: #007bff; color: white; font-size: 16px; cursor: pointer; transition: background-color 0.3s ease, transform 0.3s ease; animation: slideIn 1.4s ease-out;"
    onmouseover="this.style.backgroundColor='#0056b3';"
    onmouseout="this.style.backgroundColor='#007bff';"
    onmousedown="this.style.transform='scale(0.98)';"
    onmouseup="this.style.transform='scale(1)';"
  >
    Send
  </button>
  <p id="formMessage2" style="display: none; color: #28a745; font-weight: bold; margin-top: 15px; animation: fadeIn 1s ease-in-out;"></p>
</form>

<script>
  // Keyframe animation using JavaScript
  const styleElement = document.createElement('style');
  styleElement.textContent = `
    @keyframes fadeIn {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }
    @keyframes slideIn {
      0% { transform: translateX(-100%); }
      100% { transform: translateX(0); }
    }
  `;
  document.head.appendChild(styleElement);

  function handleFormSubmit2(event) {
    event.preventDefault(); // Prevent the default form submission

    var form = document.getElementById('contactForm2');
    var formMessage = document.getElementById('formMessage2');

    // Send the form data using Fetch API to Formspree
    fetch(form.action, {
      method: form.method,
      body: new FormData(form),
      headers: {
        'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        // Clear form fields
        form.reset();

        // Show a success message with animation
        formMessage.textContent = 'Your message has been sent successfully!';
        formMessage.style.display = 'block';
        formMessage.style.animation = 'fadeIn 1s ease-in-out';
      } else {
        formMessage.textContent = 'Oops! There was a problem submitting your form';
        formMessage.style.display = 'block';
        formMessage.style.animation = 'fadeIn 1s ease-in-out';
      }
    }).catch(error => {
      formMessage.textContent = 'Oops! There was a problem submitting your form';
      formMessage.style.display = 'block';
      formMessage.style.animation = 'fadeIn 1s ease-in-out';
    });
  }
</script>
