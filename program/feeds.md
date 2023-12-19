---
title: Relive the conference
---

<div class="feeds-full">
	<table>
  <thead>
    <td>Speaker</td>
    <td>Title</td>
    <td>Date</td>
    <td>Feed</td>
    <!--<td>Speaker link</td>-->
  </thead>
	{% for speaker in site.data.conference %}
		{% if speaker.name %}
      {% if speaker.feed %}
        <tr>
        <td><a name="{{speaker.name}}"><a href="//program/conference#{{speaker.name | replace: " ","-"}}">{{speaker.name}}</a>
        <img style="background-image: url(/assets/images/conference/{{speaker.image | default:'owasp_logo.png'}});{{speaker.style}};"></a></td>
        <td><a href="/program/conference#{{speaker.name | replace: " ","-"}}">{{speaker.title}}</a></td>
        <td><em>{{speaker.day}}</em></td>
        <td><a href="{{speaker.feed}}"><img class="youtube" src="/assets/images/conference/youtube_social_icon_red.png"></a></td>
        <td>
        {% if speaker.url %}
          <a href="{{speaker.url}}">{{speaker.urltag}}</a>
        {% endif %}
        </td>
        </tr>
      {% endif %}
		{% endif %}
	{% endfor %}
	</table>
</div>
