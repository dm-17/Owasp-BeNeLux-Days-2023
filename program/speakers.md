---
title: Speakers
---

<div class="keynote-full">

{% if site.data.conference[0].name %}
	{% assign speakers = site.data.conference %}
	<table>
	{% for speaker in speakers %}
		{% if speaker.confirmed %}
		<tr>
			<td><a href="#{{speaker.name | replace: " ","-"}}">{{speaker.name}}</a></td>
		</tr>
		{% endif %}
	{% endfor %}
	</table>

	<br><br>

	<h1>Confirmed speakers:</h1>
	<br />
	<ul>
	{% for speaker in speakers %}
		{% if speaker.confirmed %}
		<li>
        <a name="{{speaker.name | replace: " ","-"}}">
        <img style="background-image: url(/assets/images/conference/{{speaker.image | default:'owasp_logo.png'}});{{speaker.style}};"></a>
        <h2>{{speaker.name}}</h2>
      {% if speaker.bio %}
	<p>{{speaker.bio}}</p>
        <br>
      {% endif %}
      {% if speaker.title %}
        <h2>Talk: <a href="/program/talks#{{speaker.name | replace: " ","-"}}">{{speaker.title}}</a></h2>
        <br>
      {% endif %}
		</li>
      {% endif %}
	{% endfor %}
	</ul>
{% else %}
  <p><br>
     We're currently in the progress of making the conference program.<br>
     We will share the information very soon.
  </p>
{% endif %}
</div>
