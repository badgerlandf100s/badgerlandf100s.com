---
---

{%- assign align = "left" -%}
{%- for gallery in site.data.galleries.overview.albums -%}
  {%- if align == "left" -%} <div class="row"> {%- endif -%}
    <div class="half-width gallery-preview {{ align }}">
      <figure>
        <a href="{{ site.baseurl }}/albums/{{ gallery.id }}">
          <img alt="{{ gallery.title }}" src="{{ gallery.image }}" style="width: {{ site.data.galleries.overview.image_width }}" />
        </a>
        <figcaption>{{ gallery.title }}</figcaption>
      </figure>
    </div>
  {%- if align == "right" -%}
    {%- assign align = "left" -%}
    </div>
  {%- else -%}
    {%- assign align = "right" -%}
  {%- endif -%}
{%- endfor -%}
{%- if align == "right" -%} </div> {%- endif -%}
