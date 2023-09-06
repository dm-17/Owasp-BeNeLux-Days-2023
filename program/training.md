---
title: Trainings
---

<div class="keynote-full">

{% if site.data.training[0].name %}


  <h2>Trainings on 25/11/2022: Schedule</h2>
  {% assign trainings = site.data.training | sort: 'time' %}
  <table>
  {% for training in trainings %}
    {% if training.display %}
    <tr>
      <td>{{training.time}}</td>
      <td>{{training.name}}{% if training.name2 %} and {{training.name2}}{% endif %}</td>
      <td><a href="/program/training#{{training.name | replace: " ","-"}}">{{training.title}}</a></td>
    </tr>
    {% endif %}
  {% endfor %}
  </table>
  <br><br>
	<h1>Trainings on Friday 25/11/2022:</h1>
	<br />
	<ul>
	{% assign trainings = site.data.training | sort: 'name' %}
	{% for training in trainings %}
		{% if training.name %}
		<li>
        <a name="{{training.name | replace: " ","-"}}">
        <img style="background-image: url(/assets/images/training/{{training.image | default:'owasp_logo.png'}});{{training.style}};"></a>
	{% if training.name2 %}
	  <a name="{{training.namei2 | replace: " ","-"}}">
          <img style="background-image: url(/assets/images/training/{{training.image2 | default:'owasp_logo.png'}});{{training.style}}; margin-top: 210px;"></a>
	{% endif %}
      {% if training.title %}
        <h2>{{training.title}} by {{training.name}}{% if training.name2 %} and {{training.name2}}{% endif %}</h2>
      {% else %}
        <h2>{{training.name}}</h2>
      {% endif %}

      <p><em>{{training.time}}</em>
      {% if training.feed %}
          <a href="/program/feeds#{{training.name}}">Check out the streaming feed!</a>  
      {% endif %}
      </p>
      {% if training.abstract %}
        <h4>Abstract:</h4>
          <p>{{training.abstract}}</p>
          <br>
      {% endif %}
      {% if training.bio %}
        <h4>Bio:</h4>
	<p>{{training.bio}}</p>
        <br>
	{% if training.bio2 %}
	  <p>{{training.bio2}}</p>
	  <br />
	{% endif %}
      {% endif %}
		</li>
		{% endif %}
	{% endfor %}
	</ul>
{% else %}
  <p><br>
     We're currently in the progress of making the training schedule.<br>
     We will share the information very soon.
  </p>
{% endif %}
</div>
