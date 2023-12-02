# 概要

[Onirix SDK](https://docs.onirix.com/onirix-sdk)を Vite × Docker 環境で動かすリポジトリ

# 環境構築

```sh
git clone https://github.com/yoshiyasugimoto/onirix-sample
```

[Onirix](https://www.onirix.com/)にログインして SDK の Token を取得してください。
([参考 URL](https://docs.onirix.com/onirix-sdk/web-ar#onirix-studio-configurati))

```sh
echo VITE_ONIRIX_TOKEN={取得したSDK Token} > .env
```

Onirix の SDK は Onirix と契約したドメイン以外はアクセス制限がかけられています。ただし、開発用に`localhost`や`*.ngrok.io`が[ホワイトリスト](https://docs.onirix.com/onirix-sdk/web-ar#local-development-and-tes)に登録されています。また、WebAR はカメラ映像([getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia))やデバイスの方向([deviceOrientatation](https://developer.mozilla.org/en-US/docs/Web/API/Window/deviceorientation_event))を取得するために`https`でアクセスする必要があります。

```sh
ngrok http 8000
```
