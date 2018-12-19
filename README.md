# Githubの使い方

## 1. 操作前設定
編集するファイルに.gitファイルが入っているか確認する  
→入ってなければファイルの中に入ってgit init  


## 2. 基本操作  
//セーブ前の準備(commitするときは必ず行う)  
git add .（addとドットの間は半角スペース）  

//セーブ  
git commit  

//Githubに打ち上げ  
git push -u origin (ブランチ名)  

//コミット一覧  
git log  

//commitしたか、addしたか確認  
git status  

//階層構造の確認
ls

//ファイルに入る
cd ファイル名

//ファイルからでる
../

## 3. ブランチ  
//ローカルブランチの一覧  
git branch  

//新しいブランチの作成  
git checkout -b (ブランチ名)  

//ブランチの切り替え  
git checkout (ブランチ名)  

//push済みのローカルブランチの削除  
git branch --delete (ブランチ名)  

//push済みでなくともローカルブランチの削除が可能  
git branch -D (ブランチ名)  

## 4.共同開発  
//相手のリポジトリのコピー  
git clone  (コピー元URL)

//相手のリポジトリの更新差分の受け取り  
git pull 

//リポジトリの更新差分の取得
git fetch

//現在ブランチとブランチを結合する
git merge (結合ブランチ名)

※masterブランチでpullするときは作業中のブランチをコミットしてからmasterブランチに切り替える  
※masterにpullするとほかのブランチも更新される。  

<dl>
    <dt>
        1. 共同開発者はmasterブランチで開発してはいけない</dt>
    <dt>
        2. 共同開発者はこまめにmasterブランチでpullをする</dt>
    <dt>上記を必ず守ること。</dt>
</dl>

## 5プルリクエスト  
//打ち上げたいリポジトリの指定  
git remote add origin (追加したいリポジトリURL)  

//ブランチを打ち上げる  
git push -u origin (ブランチ名)  

その後、Githubページに移動してプルリクエストを完了する。  

## 6コンフリクト
編集後はコミットすること！
git merge --continuedeでaddとcommitを同時に行える！


下記では通常の方法でコンフリクトの改善が見込めない場合の方法を記載する。  

//コミットをさかのぼる(コミットは削除されない)  
git revert (コミットシリアル値)  

//コミットをなかったことにする  
git reset (コミットシリアル値)  
