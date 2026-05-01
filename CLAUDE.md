# CLAUDE.md — optcg-deck プロジェクトルール

## バージョン管理

**コードを変更するたびに必ずバージョンを更新すること。**

バージョン番号は以下の3か所を常に同じ値にする:

1. `<title>` タグ (index.html 6行目)
2. ロゴ表示の `<span>` (index.html 内 `.logo` の span)
3. JSコメント `// OP·TCG BUILDER vX.X.X` (index.html の script 冒頭)

### バージョニング規則

| 変更の種類 | 上げるべき桁 | 例 |
|-----------|-------------|-----|
| バグ修正・小改善 | パッチ (X.X.**Z**) | 2.1.2 → 2.1.3 |
| 新機能追加・UI改善 | マイナー (X.**Y**.0) | 2.1.3 → 2.2.0 |
| 大規模リファクタリング | メジャー (**X**.0.0) | 2.x.x → 3.0.0 |

### 更新方法

```bash
# 現在のバージョン確認
grep -n "v2\." index.html

# 一括置換例 (2.1.3 → 2.1.4)
# Edit ツールで replace_all:true を使う
```

## ブランチ・デプロイ

- 開発ブランチ: `claude/explore-features-p2QaY`
- 変更後は必ず commit & push すること
- **GitHub Pages は `main` ブランチを参照しているため、変更後は必ず `main` にもマージすること**

```bash
git checkout main
git merge claude/explore-features-p2QaY --no-edit
git push origin main
git checkout claude/explore-features-p2QaY
```
