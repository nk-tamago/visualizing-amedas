# visualizing-amedas
アメダスの観測所と気象情報を地図上に可視化します

## Description
- データの取得は気象庁の公開APIではありませんが下記リンクを参照すると「政府標準利用規約に準拠してご利用いただけます」とのことで、規約に準拠して利用しています
  - https://sumatome.com/su/1364504338572410885
  - https://forest.watch.impress.co.jp/docs/serial/yajiuma/1309318.html
- 「お手軽＆コピペで感動を与える」を目的として作成したため、1ファイル縛りとしています。また例外処理やクラス設計などはしていません

- 解説
  - `generateGeoJsonAmedasVoronoiPolygons()`
    - アメダス観測所データとアメダス気象情報データをAPIから取得します。
    - 取得したデータを元にボロノイ図も作成し陸地でクリッピングしたポリゴンを生成します。
  - `initializeMainMap()`
    - [leaflet](https://leafletjs.com/)を使う上での必要な前処理や初期化を行います。
  - `initializePanels()`
    - 地図以外の情報を表示するレイヤパネル、情報パネル、凡例パネルを初期化し画面上に配置します。
    - 情報パネルと凡例パネルは[Leafletの公式チュートリアル](https://leafletjs.com/examples/choropleth/)を参考にしています。めちゃくちゃ有能な公式ページです。
  - `initializeBaseMaps()`
    - 背景に表示するベースとなる地図を初期化し背景図として使用できるようにします。
  - `initializeOverlayMaps()`
    - 読み込んだアメダス観測所データをオーバーレイレイヤとして初期化し使用できるようにします。
  - `main()`
    - 本アプリのメイン処理です。上記のメソッドを呼び出します。

## Usage
index.html をコピペまたはダウンロードしてください

## Demo
https://nk-tamago.github.io/visualizing-amedas/


