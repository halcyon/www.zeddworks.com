---
layout: page
title: Contact
permalink: /contact/
weight: 5
---
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3306.9897743829265!2d-84.1398910490016!3d34.018473426860886!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x88f598794fa590ab%3A0x15800e05f32491c1!2sRachel+Lacy%2C+Psy.D.%2C+P.C.!5e0!3m2!1sen!2sus!4v1465093154765" width="600" height="450" frameborder="0" style="border:0" allowfullscreen></iframe>


<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>

<script>
  $(document).ready(function() {
    $('#contact').submit(function(event) {
      $.ajax({
        url: 'https://rqxk18y88g.execute-api.us-east-1.amazonaws.com/production/submit',
        method: 'POST',
        data: $('#contact').serialize(),
        dataType: 'json'});
      event.preventDefault();
    });
  });
</script>

<form id="contact" method="post">
  Name:<br>
  <input type="text" name="name"><br>
  Email:<br>
  <input type="text" name="email"><br>
  Phone:<br>
  <input type="text" name="phone"><br>
  Message:<br>
  <textarea name="message" cols="48" rows="10" maxlength="500"></textarea>
  <input type="submit" value="Submit">
</form>

### Office Hours are Monday through Thursday 10 am to 6 pm

* Neuropsychological and behavioral medicine services are offered to adults and adolescents
* Psychotherapy for psychiatric disorders is offered to individuals age 16 and older

## Insurance
* Medicare
* Tricare

### Rachel Lacy, Psy.D., ABPP

Dr. Lacy’s credentials include a Master’s in Guidance and Counseling
from the University of Georgia, and Master’s and Doctoral degrees in
Clinical Psychology from Georgia School of Professional
Psychology. She received specialized training in neuropsychological
assessment from Emory Center for Rehabilitation Medicine and completed
her internship in neuropsychology and behavioral medicine at the
University of Miami Medical School/ Jackson Memorial Hospital. Her two
year post-doctoral residency was completed at The Center for Cognitive
Rehabilitation in Decatur, Georgia under the supervision of Stephen
J. Johnson, Ph.D., ABPP, and John R. Sass, Ph.D. Dr. Lacy is a member
of the American Psychological Association, National Academy of
Neuropsychology, International Neuropsychological Society, American
Academy of Pain Management, and National Register of Health Service
Providers.

#### National Register of Health Service Providers
* [National Register](http://www.nationalregister.org)
* [Find a Psychologist](http://www.findapsychologist.org)
