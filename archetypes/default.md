---
draft: true
translationKey: {{ .File.Dir }}{{ if ne .File.TranslationBaseName "_index" | and (ne .File.TranslationBaseName "index") }}{{ .File.ContentBaseName }}{{ end }}
title: {{ i18n .Name | default (replace .Name "-" " ") | title }}
slug: {{ i18n .Name | default .Name | lower | urlize }}
date: {{ .Date }}
url: {{ relLangURL "" }}{{ range $word := split .File.Dir "/" }}{{ with $word }}{{ i18n $word | default $word | lower | urlize }}/{{end}}{{ end }}{{ if ne .File.TranslationBaseName "_index" | and (ne .File.TranslationBaseName "index") }}{{ i18n .Name | default .Name | lower | urlize }}{{ end }}
aliases:
  - {{ .File.Dir | relLangURL }}{{ if ne .File.TranslationBaseName "_index" }}{{ .File.ContentBaseName }}{{ end }}
---
