# aisss_extensions
SONY製イメージセンサーIMX500を軸にしたプラットフォームサービス「AITRIOS」のファンによる「AITRIOS」の機能を非公式に拡張する開発ライブラリのリポジトリです。<br/>

# 主な機能
物体認識の推論結果をデシリアライズする<br/>

# 仕様イメージ
Azure FunctionsのHTTPトリガーを用い、物体認識の推論結果の文字列をBody句に渡すと、デシリアライズした結果が返ってきます。<br/>
Flatbuffersを用いて、デシリアライズを実施しています。<br/>
get_deserialize_data関数及び周辺の処理を流用することで、Azure Functions以外の仕組みにも組み込み／活用することができます。<br/>

# 実行時のイメージ
https://aisss-extensions.azurewebsites.net/api/DeserializeInference?code={code}<br/>
aisss-extensions.azurewebsites.netはお使いの環境によって変更してください。<br/>
codeはAzure Functionsで関数作成時に発行されたコードを利用してください。<br/>

Body句には推論結果をそのまま渡してください。以下は実際に出力された推論結果データの例となります。<br/>
{"DeviceID":"Aid-80070001-0000-2000-9002-000000000a66","ModelID":"0311030023160100","Image":false,"Inferences":[{"T":"20240916160111994","O":"DAAAAAAABgAKAAQABgAAAAwAAAAAAAYACAAEAAYAAAAEAAAAAQAAABAAAAAMABAAAAAHAAgADAAMAAAAAAAAARQAAAAAAHI/DAAUAAQACAAMABAADAAAAK4AAAAMAAAAHwEAAGEAAAA="}]}
