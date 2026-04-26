### 1. NGFW (Next Generation Firewall) >> pfweb.png + proof.png
- Развёрнута ВМ с pfSense CE 2.6.0 (1 GB RAM, 3–4 GB disk, 1 vCPU)
- Настроены WAN/LAN интерфейсы, доступ к веб-интерфейсу
- Создан пользователь в группе `admins`

### 2. IPSec Site-to-Site VPN >> site-to-site.png + pfsense1.xml + pfsense2.xml
- Клонирована ВМ для эмуляции второго узла
- Настроен Site-to-Site IPSec VPN между двумя pfSense (IKEv2, ESP, DH-группа)
- Проверено установление туннеля в фазе 1 и 2
- Экспортированы конфигурации (`pfsense1.xml`, `pfsense2.xml`)
- Cтатус туннеля: `site-to-site.png`

### 3. Правила межсетевого экранирования >> fw_rules.xml
Созданы и применены правила на pfSense:
-  Блокировка входящих RDP-подключений из локальной сети
-  Разрешение SMTP только в рабочее время (07:00–22:59, выбранный день недели)
-  Блокировка SSH-доступа из локальной сети
- Экспорт конфигурации: `fw_rules.xml`

### 4.  Те же правила на Bash >> iptables_rules.txt
