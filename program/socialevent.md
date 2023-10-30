---
title: Social event
---

<div class="social-event">

  <p>
  On Thursday evening we organize a social event in Cegeka's offices on the Corda Campus..<br />
You are welcome to join us for a dinner as of 18:00.<br /><br />
Sorry, the social event is currently <font style="color: red">sold out</font>! <br /><br />

We will provide a networking reception with snacks and drinks. <br />
Drinks are kindly offered by:
  </p>

{% assign socialEventSponsors = site.data.sponsors | where:"level","Social event" | sort: 'name' %}

  {% if socialEventSponsors %}
    {% for sponsor in socialEventSponsors %}
      <div class="socialevensponsor">
        <a href="{{ sponsor.url }}" target="_blank"><img src="/assets/images/sponsors/{{ sponsor.image }}" alt="{{ sponsor.name }} logo" style="{{ sponsor.style }}"/></a><br />
      </div>
    {% endfor %}
  {% endif %}

</div>
