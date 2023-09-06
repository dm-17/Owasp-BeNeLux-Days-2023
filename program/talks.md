---
title: Talks
---

<div class="keynote-full">

{% if site.data.conference[0].name %}
	{% assign speakers = site.data.conference %}
	<table>
	{% for speaker in speakers %}
		{% if speaker.confirmed %}
		<tr>
			<td><a href="/program/talks#{{speaker.name | replace: " ","-"}}">{{speaker.title}}</a></td>
		</tr>
		{% endif %}
	{% endfor %}
	</table>

	<br><br>

	<h1>Confirmed talks:</h1>
	<br />
	<ul>
	{% for speaker in speakers %}
		{% if speaker.confirmed %}
		<li>
        		<a name="{{speaker.name | replace: " ","-"}}">
        		<img style="background-image: url(/assets/images/conference/{{speaker.image | default:'owasp_logo.png'}});{{speaker.style}};"></a>
        		<h2>{{speaker.title}} by <a href="/program/speakers#{{speaker.name | replace: " ","-"}}">{{speaker.name}}</a></h2>
        		<p>{{speaker.abstract}}</p>
        		<br>
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
