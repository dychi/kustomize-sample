# Kustomizeの練習用リポジトリ
kustomizeのインストール for Mac(Kubernetes1.14からkubectlに統合されているらしいが、細かいコマンドを使うならインストールした方が良さそう)
```
brew install kustomize
```

ディレクトリ構成
```
.
├── README.md
├── base
│   ├── deployment.yaml
│   └── kustomization.yaml
└── overlays
    ├── development
    │   ├── deployment.yaml
    │   └── kustomization.yaml
    └── staging
        ├── deployment.yaml
        └── kustomization.yaml
```

## overlaysで変更した内容を確認する方法
```
kustomize build overlays/staging
```
もしくは
```
kubectl kustomize overlays/staging
```

## 変更前と変更後の差分を確認する方法
```
diff <(kustomize build base) <(kustomize build overlays/staging)
```

## 参考リンク
- [Introduction to kustomize](https://speakerdeck.com/spesnova/introduction-to-kustomize)
- [Kustomizeを利用してk8sの構成管理をシンプルにやってみる](https://caddi.tech/archives/427)