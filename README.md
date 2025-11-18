# @novalumo/biome-config

## Installation

```bash
bun add @novalumo/biome-config --dev
```

## Development

### Release

このプロジェクトは [changesets](https://github.com/changesets/changesets) を使用して自動リリースを行います。

#### リリースフロー

1. **変更を加えた後、changeset を作成**

   ```bash
   bun run changeset
   ```

   対話形式で以下を入力:
   - バージョンアップの種類 (major/minor/patch)
   - 変更内容の説明

2. **PR を作成してレビュー**

   changeset ファイル (`.changeset/*.md`) を含めて PR を作成し、main ブランチにマージします。

3. **自動的に Version Packages PR が作成される**

   GitHub Actions が自動的に "Version Packages" という PR を作成します。
   この PR には以下が含まれます:
   - `package.json` のバージョン更新
   - `CHANGELOG.md` の更新

4. **Version Packages PR をマージして公開**

   Version Packages PR をマージすると、GitHub Actions が自動的に以下を実行します:
   - npm へのパッケージ公開
   - Git タグの作成 (例: `v0.0.7`)
   - GitHub Release の作成 (CHANGELOG 付き)

#### 手動公開 (非推奨)

通常は使用しませんが、必要な場合は以下のコマンドで手動公開できます:

```bash
npm publish
```

**注意**: 手動公開する場合は、事前に `bun run version` でバージョンを更新してください。
