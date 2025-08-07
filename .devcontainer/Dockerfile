FROM mcr.microsoft.com/devcontainers/base:ubuntu

RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    zip \
    xz-utils \
    libglu1-mesa \
    openjdk-17-jdk \
    npm \
    && rm -rf /var/lib/apt/lists/*

RUN npm install -g firebase-tools

ENV ANDROID_SDK_ROOT=/opt/android-sdk
ENV PATH="${ANDROID_SDK_ROOT}/cmdline-tools/latest/bin:${ANDROID_SDK_ROOT}/platform-tools:${PATH}"

RUN mkdir -p ${ANDROID_SDK_ROOT}/cmdline-tools \
    && curl -o commandlinetools.zip https://dl.google.com/android/repository/commandlinetools-linux-11076708_latest.zip \
    && unzip commandlinetools.zip -d ${ANDROID_SDK_ROOT}/cmdline-tools \
    && mv ${ANDROID_SDK_ROOT}/cmdline-tools/cmdline-tools ${ANDROID_SDK_ROOT}/cmdline-tools/latest \
    && rm commandlinetools.zip

RUN yes | sdkmanager --licenses
RUN sdkmanager "platform-tools" "platforms;android-33" "build-tools;34.0.0"

ENV FLUTTER_HOME=/opt/flutter
ENV PATH="${FLUTTER_HOME}/bin:${FLUTTER_HOME}/bin/cache/dart-sdk/bin:${PATH}"

RUN git clone https://github.com/flutter/flutter.git ${FLUTTER_HOME} \
    && flutter doctor

RUN flutter upgrade \
    && flutter config --enable-web \
    && flutter config --android-sdk ${ANDROID_SDK_ROOT} \
    && flutter precache

RUN groupadd --gid 1000 vscode && useradd -m -u 1000 -g vscode vscode
USER vscode
WORKDIR /workspaces
