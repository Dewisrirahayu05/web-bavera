---
title: "Activity Schedule"
permalink: /schedule/
layout: page
---
# 📅 Kalender Kegiatan UKM BAVERA

<table>
  <thead>
    <tr>
      <th>Nama Kegiatan</th>
      <th>Hari</th>
      <th>Tanggal</th>
      <th>Waktu</th>
      <th>Tempat</th>
      <th>Jenis</th>
      <th>Platform</th>
    </tr>
  </thead>
  <tbody>
    {% assign now = site.time | date: "%Y-%m-%d" %}

    {% assign kegiatan = site.data.jadwal %}

    {% for item in kegiatan %}
      {% assign tanggal = item.tanggal | date: "%Y-%m-%d" %}
      {% if tanggal < now %}
        {% assign coret = "style='text-decoration: line-through; color: gray;'" %}
      {% else %}
        {% assign coret = "" %}
      {% endif %}
    <tr>
      <td {{ coret }}>{{ item.nama }}</td>
      <td {{ coret }}>{{ item.hari }}</td>
      <td {{ coret }}>{{ item.tanggal }}</td>
      <td {{ coret }}>{{ item.waktu }}</td>
      <td {{ coret }}>{{ item.tempat }}</td>
      <td {{ coret }}>{{ item.jenis }}</td>
      <td {{ coret }}>{{ item.platform }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
