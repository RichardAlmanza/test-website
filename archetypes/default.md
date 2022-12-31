---
translationKey: {{ replace .File.Path ".md" "" }}
title: {{ replace .Name "-" " " | title }}
slug: {{ replace (i18n .Name | lower) " " "-" }}
date: {{ .Date }}
draft: true
---

