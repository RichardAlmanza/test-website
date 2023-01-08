---
draft: false
translationKey: {{ .File.Dir }}{{ if ne .File.TranslationBaseName "_index" | and (ne .File.TranslationBaseName "index") }}{{ .File.ContentBaseName }}{{ end }}
title: {{ i18n .Name | default (replace .Name "-" " ") | title }}
slug: {{ i18n .Name | default .Name | lower }}
date: {{ .Date }}
url: {{ relLangURL "" }}{{ range $word := split .File.Dir "/" }}{{ with $word }}{{ i18n $word | default $word | lower }}/{{end}}{{ end }}{{ if ne .File.TranslationBaseName "_index" | and (ne .File.TranslationBaseName "index") }}{{ i18n .Name | default .Name | lower }}{{ end }}
aliases:
  - {{ .File.Dir | relLangURL }}{{ if ne .File.TranslationBaseName "_index" }}{{ .File.ContentBaseName }}{{ end }}

banner: img/products/
categories: {{ range $section := split .File.Dir "/" }}{{ with $section }}
  - {{ i18n $section | default $section | lower }}{{ end }}{{ end }}
authors:
  - SKYPLUS
  - JAICO
---
