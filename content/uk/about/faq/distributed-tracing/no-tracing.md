---
title: Чому мої запити не відстежуються?
weight: 30
---

З початку версії Istio 1.0.3 швидкість вибірки для трейсингу була зменшена до 1% в [конфігураційному профілі `default`](/docs/setup/additional-setup/config-profiles/). Це означає, що лише 1 з 100 трейсів, захоплених Istio, буде надіслано до бекенда для трейсингу. Швидкість вибірки в профілі `demo` все ще встановлена на 100%. Дивіться [цей розділ секцію](/docs/tasks/observability/distributed-tracing/mesh-and-proxy-config/#customizing-trace-sampling) для отримання додаткової інформації про те, як налаштувати швидкість вибірки.

Якщо ви все ще не бачите дані трейсингу, будь ласка, переконайтесь, що ваші порти відповідають [конвенціям іменування портів](/about/faq/#naming-port-convention) в Istio і що відповідний порт контейнера відкритий (наприклад, через специфікацію podʼа), щоб дозволити захоплення трафіку sidecar проксі (Envoy).

Якщо ви бачите дані трейсингу тільки для egress-проксі, але не для ingress-проксі, це також може бути повʼязано з [конвенціями іменування портів](/about/faq/#naming-port-convention). Починаючи з [Istio 1.3](/news/releases/1.3.x/announcing-1.3/#intelligent-protocol-detection-experimental), протокол для **вихідного** трафіку визначається автоматично.
