---
title: Conference program
---

<div class="keynote-full">

{% if site.data.conference[0].name %}
	{% assign speakers = site.data.conference | sort: 'time' %}
	<h1>Conference day: full schedule</h1>
	<table>
	{% for speaker in speakers %}
		<tr>
			<td>{{speaker.time}}</td>
		{% if speaker.display %}
			<td>{{speaker.name}}</td>
			<td><a href="/program/conference#{{speaker.name | replace: " ","-"}}">{{speaker.title}}</a></td>
		{% else %}
			<td colspan="2" align="center">{{speaker.title}}
			{% if speaker.name %}
				by {{speaker.name}}
			{% endif %}
			</td>
		{% endif %}
		<td>
		{% if speaker.feed %}
		<a href="{{speaker.feed}}"><img class="youtube" src="/assets/images/conference/youtube_social_icon_red.png"></a>
		{% endif %}
		</td>
		</tr>
	{% endfor %}
	</table>

	<br><br>

	<h1>Confirmed speakers for Thursday 24/11/2022:</h1>
	<br />
	<ul>
	{% for speaker in speakers %}
		{% if speaker.display %}
		<li>
        <a name="{{speaker.name | replace: " ","-"}}">
        <img style="background-image: url(/assets/images/conference/{{speaker.image | default:'owasp_logo.png'}});{{speaker.style}};"></a>
      {% if speaker.title %}
        <h2>{{speaker.title}} by {{speaker.name}}</h2>
      {% else %}
        <h2>{{speaker.name}}</h2>
      {% endif %}

      <p><em>{{speaker.time}}</em>
      {% if speaker.feed %}
          - <a href="/program/feeds#{{speaker.name}}">Check out the streaming feed!</a>
      {% endif %}
      </p>

      {% if speaker.abstract %}
			<br>
        <h4>Abstract:</h4>
          <p>{{speaker.abstract}}</p>
          <br>
      {% endif %}
      {% if speaker.bio %}
        <h4>Bio:</h4>
	<p>{{speaker.bio}}</p>
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
