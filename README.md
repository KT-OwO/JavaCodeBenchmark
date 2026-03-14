# Java Benchmark Calculation

## 概要

このプロジェクトは、JMH（Java Microbenchmark Harness）を使用したJavaコードのマイクロベンチマークツールです。異なる実装方法のパフォーマンスを正確に測定し、比較することができます。

## 技術スタック

- Java 17
- JMH 1.37（OpenJDK Java Microbenchmark Harness）
- Maven 3.x

## プロジェクト構成

- `src/main/java/com/example/MyBenchmark.java`: ベンチマーク実装のサンプルコード
- `pom.xml`: Mavenプロジェクト設定ファイル（JMH依存関係とビルド設定を含む）

## ベンチマーク設定

現在のベンチマーク設定:

- **測定モード**: Throughput（スループット）、AverageTime（平均時間）、SampleTime（サンプル時間分布）
- **出力単位**: ナノ秒
- **ウォームアップ**: 5イテレーション、各1秒
- **測定**: 10イテレーション、各1秒
- **Fork**: 3回

## ビルド方法

```bash
mvn clean package
```

このコマンドにより、JMHベンチマークを実行可能なFat JARファイルが生成されます。

## 実行方法

```bash
java -jar target/jbc-1.0-SNAPSHOT.jar
```

## ベンチマーク例

プロジェクトには、以下の2つの実装を比較するサンプルベンチマークが含まれています:

- `implA()`: 通常の加算演算子を使用
- `implB()`: `Math.addExact()`メソッドを使用

## カスタマイズ

独自のベンチマークを追加する場合は、`MyBenchmark.java`を参考に、`@Benchmark`アノテーションを付けたメソッドを作成してください。パラメータ化されたベンチマークの例もコメントとして含まれています。

## ライセンス

このプロジェクトのライセンスについては、LICENSEファイルを参照してください。