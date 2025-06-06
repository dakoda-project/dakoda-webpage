---
layout: page
permalink: /team/
title: Team
description: Mitglieder des DAKODA-Projekts.
nav: true
nav_rank: 5
---

{% assign groups = site.members | sort: "group_rank" | map: "group" | uniq %}
{% for group in groups %}
## {{ group }}

    {% assign members = site.members | sort: "member_rank" | where: "group", group %}
    {% assign members = site.members | sort: "lastname" | where: "group", group %}
    {% for member in members %}
<p>
    <div class="card {% if member.inline == false %}hoverable{% endif %}">
        <div class="row no-gutters">
            <div class="col-sm-4 col-md-3">
                <img src="{{ '/assets/img/' | append: member.profile.image | relative_url }}" class="img-fluid" alt="{{ member.profile.name }}" />
            </div>
            <div class="team col-sm-8 col-md-9">
                <div class="card-body">
                    {% if member.inline == false %}<a href="{{ member.url | relative_url }}">{% endif %}
                    <h5 class="card-title">{{ member.profile.name }}</h5>
                    {% if member.profile.position %}<h6 class="card-subtitle mb-2 text-muted">{{ member.profile.position }}</h6>{% endif %}
                    <p class="card-text">
                        {{ member.teaser }}
                    </p>
                    {% if member.inline == false %}</a>{% endif %}
                    {% if member.profile.email %}
                        <a href="mailto:{{ member.profile.email }}" class="card-link"><i class="fas fa-envelope"></i></a>
                    {% endif %}
                    {% if member.profile.phone %}
                        <a href="tel:{{ member.profile.phone }}" class="card-link"><i class="fas fa-phone"></i></a>
                    {% endif %}
                    {% if member.profile.orcid %}
                        <a href="https://orcid.org/{{ member.profile.orcid }}" class="card-link" target="_blank"><i class="fab fa-orcid"></i></a>
                    {% endif %}
                    {% if member.profile.twitter %}
                        <a href="https://twitter.com/{{ member.profile.twitter }}" class="card-link" target="_blank"><i class="fab fa-twitter"></i></a>
                    {% endif %}
                    {% if member.profile.github %}
                        <a href="https://github.com/{{ member.profile.github }}" class="card-link" target="_blank"><i class="fab fa-github"></i></a>
                    {% endif %}
                    {% if member.profile.website %}
                        <a href="{{ member.profile.website }}" class="card-link" target="_blank"><i class="fas fa-globe"></i></a>
                    {% endif %}
                    <p class="card-text">
                        <small class="test-muted"><i class="fas fa-thumbtack"></i> {{ member.profile.address | replace: '<br />', ', ' }}</small>
                    </p>
                </div>
            </div>
        </div>
    </div>
</p>
<br/>
    {% endfor %}
{% endfor %}

## Wissenschaftlicher Beirat
**Christine Czinglar** <br>
Professorin für Deutsch als Zweit- und Fremdsprache an der Friedrich-Schiller-Universität Jena

**Stefanie Dipper** <br>
Professorin für Computerlinguistik an der Ruhr-Universität Bochum, Lehrstuhl für Linguistik und Projektleitung des SFB-Projekts C6

**Jana Gamper** <br>
Professorin für Deutsch als Zweitsprache an der Justus-Liebig-Universität Gießen

**Gisela Håkansson** <br>
Emeritierte Professorin für Allgemeine Linguistik an der Universität Lund

**Hagen Hirschmann** <br>
Wissenschaftlicher Mitarbeiter am Institut für Deutsche Sprache und Linguistik der Humboldt-Universität zu Berlin, Abteilung Korpuslinguistik und Morphologie

**Anke Lenzing** <br>
Professorin für Fachdidaktik in Englisch, Universität Innsbruck

**Detmar Meurers** <br>
Leiter der Arbeitsgruppe Sprache und KI in der Bildung am Leibniz Institut für Wissensmedien (IWM) und Professor für Computerlinguistik, Universität Tübingen

**Elena Volodina** <br>
Forscherin am Fachbereich Schwedisch, Mehrsprachigkeit, Sprachtechnologie an der Universität Göteborg

**Sonja Zimmermann** <br>
Test-DaF-Institut/g.a.s.t
