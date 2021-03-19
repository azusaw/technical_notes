# Neo4j

#### 概要

- GraphDBの一種で、オープンソースでは最も人気
- グラフ構造でデータを保存するので、探索効率が高くRDBを遥かにしのぐパフォーマンスを持つ
- `index-free adjacency`という性質が速さのカギだが、この性質ゆえ遅くなることもあるらしく、そのため大規模サービスでの採用は難しい（ノードのリレーションが1万以上に達した場合との論文もあり）

#### 参考URL

https://the.igreque.info/posts/2014-06-08-neo4j.html


# Cypher QL

#### 概要

- Neo4jのグラフ構造のデータ処理を行うために開発されたSQLライクなクエリ言語

#### 使用例

```
CREATE
	(item:Item {
		item_id: "123456789",
		mtime: timestamp()
	})

RETURN item
MATCH (item:Item { item_id: "123456789" }),
      path=(srv1)-[*]-()
RETURN path


MATCH (n:ServiceAdaptorL3)--(branch:Branch) RETURN n, branch LIMIT 25

```



#### 参考URL

https://www.creationline.com/lab/7685

https://www.deep-rain.com/programming/database/880
