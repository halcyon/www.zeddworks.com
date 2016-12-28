---
layout: page
title: Contact
permalink: /contact/
weight: 5
---
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3306.9897743829265!2d-84.1398910490016!3d34.018473426860886!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x88f598794fa590ab%3A0x15800e05f32491c1!2sRachel+Lacy%2C+Psy.D.%2C+P.C.!5e0!3m2!1sen!2sus!4v1465093154765" width="678" height="450" frameborder="0" style="border:0" allowfullscreen></iframe>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<script src="https://cdn.jsdelivr.net/parsleyjs/2.6.0/parsley.min.js"></script>
<script src="../js/bootstrap.min.js"></script>

<div class="modal fade" id="submission" tabindex="-1" role="dialog">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
        <h4 class="modal-title">Submitting message &hellip;</h4>
      </div>
      <div class="modal-body">
        <div class="progress">
          <div class="progress-bar" role="progressbar" aria-valuenow="0" aria-valuemax="100">
          </div>
        </div>
        <div id="delivered" class="alert alert-success" role="alert" style="display:none;">
          Message Delivered.
        </div>
        <div id="failed" class="alert alert-danger" role="alert" style="display:none;">
          <p>Message delivery failed.</p>
          <p>Please leave a message with Dr. Lacy's office at 770-722-7827.</p>
        </div>
      </div>
    </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
</div><!-- /.modal -->

<script>
  function failure() {
    $('.progress-bar').attr('aria-valuenow',100);
    $('#failed').fadeIn();
  }

  $(document).ready(function() {
    $('#contact').parsley();
    $('#contact').submit(function(event) {
      $('#delivered').hide();
      $('#failed').hide();
      $('.progress-bar').attr('aria-valuenow',0)
      $('#submission').modal({keyboard: false,
                              backdrop: false});
      $('.progress-bar').each(function() {
        var $bar = $(this);
        var progress = setInterval(function() {

          var currWidth = parseInt($bar.attr('aria-valuenow'));
          var maxWidth = parseInt($bar.attr('aria-valuemax'));

          //update the progress
          $bar.width(currWidth+'%');
          $bar.attr('aria-valuenow',currWidth+1);

          //clear timer when max is reach
          if (currWidth >= maxWidth){
            clearInterval(progress);
          }
        }, 400);
      });
      $.ajax({
      url: 'https://m9p097qv56.execute-api.us-east-1.amazonaws.com/production/submit',
        method: 'POST',
        data: $('#contact').serialize(),
        dataType: 'json'
      })
      .done(function(data, textStatus, jqXHR) {
        if (jqXHR.responseText='{"code":0,"error":"SUCCESS","message":"messages sent"}') {
          $('.progress-bar').attr('aria-valuenow',100);
          $('#delivered').fadeIn();
          setInterval(function() {
            $('#submission').modal('hide');
            $('#contact').hide();
          }, 3000);
        } else {
          failure();
        }
      })
      .fail(function(data) {
        failure();
      });
      event.preventDefault();
    });
  });
</script>

<div class="panel panel-primary">
  <div class="panel-body">
    <form id="contact" method="post">
      <div class="form-group">
        <label for="name">Full Name</label>
        <input type="text" name="name" class="form-control" id="name" required="" data-parsley-error-message="Your name is required.">
      </div>

      <div class="form-group">
        <label for="email">Email</label>
        <input type="text" name="email" class="form-control" id="email" data-parsley-type="email">
      </div>

      <div class="form-group">
        <label for="phone">Phone</label>
        <input type="text" name="phone" class="form-control" id="phone" required="" data-parsley-error-message="Your phone number is required.">
      </div>

      <div class="form-group">
        <label for="message">Message</label>
        <textarea name="message" class="form-control" id="message" rows="10" maxlength="500" required="" data-parsley-error-message="Your message is required."></textarea>
      </div>

      <fieldset class="account-action">
        <button class="btn btn-primary" type="submit">Submit</button>
      </fieldset>
    </form>
  </div>
</div>

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
