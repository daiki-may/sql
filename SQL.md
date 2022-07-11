# SQL構文
- **利用するデータベースの宣言**  
use データベース名;  
ex) use mydb;

- **全データ取得**  
select * from テーブル名  
ex) select * from products;

- **列を指定してデータ取得**  
select 列1,列2 from テーブル名;  
ex) select id,last_name from users;

- **列に別名をつける(asはなくても良い)**  
select 列1 as new列1,列2 as new列2 from テーブル名;  
ex) select name as 名前, price as 価格 from products;

- **列に計算結果を入れて別名をつける**  
select 列1 * 1.1 as new列1 from テーブル名;  
ex) select price * 1.1 as 価格 from products;

- **条件指定をしてデータを取り出す**  
select 列1,列2 from テーブル名 where 条件;  
ex) select name, price from products where price >= 9800;
	- **条件に使う演算子**  
		- idが1,2,3の行を取得  
		select * from テーブル名 where id in (1,2,3);  
		- idが1,2,3の行以外を取得  
		select * from テーブル名 where id not in (1,2,3);  
		- idがnullの行を取得  
		select * from テーブル名 where id is null;  
		- idがnull以外の行を取得  
		select * from テーブル名 where id is not null;  
		- priceが1000から1900の行を取得  
		select * from テーブル名 where porice between 1000 and 1900;  
		- 論理積,論理和(where price >= 1000 and price <= 1900, where price = 1000 or price = 1900)  

- **パターンマッチング**  
select 列1 from テーブル名 where 列名 like ワイルドカード文字;  
- **ワイルドカード文字について**  
	- '%'→0文字以上の任意の文字列  
	('中%'→'中'から始まる文字列)('%中%'→'中'を含む文字列)('%子'→'子'で終わる文字列)  
	- '_'→任意の1文字  
	('__子'→何かしらの2文字から始まり'子'で終わる文字列)  

- **取得件数を制限**  
select 列1 from テーブル名 limit 10;  
ex) select price from products limit 10;  
select 列1 from テーブル名 limit 7,10;→8番目から10件  
ex) select price from products limit 7,10;  