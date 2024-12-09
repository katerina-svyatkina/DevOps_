FROM jenkins/jenkins:lts

USER root

# Установка Ansible, sshpass и Python
RUN apt-get update && apt-get install -y \
    ansible \
    sshpass \
    python3-pip \
    python3-venv \
    && apt-get clean

# Настройка виртуального окружения Python (если нужно)
RUN python3 -m venv /opt/venv && \
    /opt/venv/bin/pip install --upgrade pip && \
    /opt/venv/bin/pip install docker

# Устанавливаем переменные окружения, чтобы Jenkins использовал виртуальное окружение
ENV PATH="/opt/venv/bin:$PATH"

USER jenkins
