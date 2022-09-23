## 4.6.1
Скриншот:
https://yadi.sk/i/3mvMw_y4h3khvg

Использовал filebeat.
Пришлось дописать конфиг самого модуля kibana, указав путь к файлу логов. Без этого не подхватывал логи.

## 4.6.2
Скриншот:
https://yadi.sk/i/75Umi5hrvZ97fg

В моем варианте: \
server1 = c4.6.1, 10.129.0.16 \
server2 = c4.6.4, 10.129.0.16

Использовал filebeat вместо rsyslog.
Кроме конфиг файлов filebeat + module nginx добавляю измененный конфиг файл elasticsearch.yml с server2:
1) указал network.host: 0.0.0.0, чтобы был доступен извне
2) добавил cluster.initial_master_nodes: node-1, без этого Эластик не хочет принимать настройку network.host
