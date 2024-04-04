# otus-troubleshooting


# Найти путь пакета через систему
mount -t debugfs none /sys/kernel/debug
sudo docker run --privileged --rm -t --pid=host -v /sys/kernel/debug/:/sys/kernel/debug/ cilium/pwru pwru --output-tuple 'host 8.8.8.8'

# Отследить IO latency за 10 секунд
dnf install bpftrace
sudo timeout 10 ./io_latency.bt
