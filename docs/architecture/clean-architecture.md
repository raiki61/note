# Clean Architecture

## 実装クリーンアーキテクチャ
![](/out/docs/architecture/clean-architecture/%E5%AE%9F%E8%A3%85%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%A2%E3%83%BC%E3%82%AD%E3%83%86%E3%82%AF%E3%83%81%E3%83%A3.svg)


クリーンアーキテクチャは、ソフトウェアの設計原則として、システムを疎結合で保ち、テストや変更の容易さを向上させるために使用されます。以下に、クリーンアーキテクチャの要素とそれらの関係を日本語でわかりやすく説明します。

ドメイン層：
- エンティティ: システムの中核的なビジネスルールを表現します。データとロジックを含み、他の層に依存しません。
- ユースケース: システムのユースケースや操作を実現するためのビジネスルールを実装します。エンティティと協力して動作し、他の層に依存しません。

アプリケーション層：
- サービス: ユースケースの具体的な実装を提供します。ユースケースの流れやトランザクションの管理などを担当し、ドメイン層とインターフェースアダプタ層の間を調整します。

インターフェースアダプタ層：
- プレゼンター: ユーザーインターフェースの表示や表示データの整形を行います。ユースケースの実行結果を受け取り、ユーザーに適切な形式で表示します。
- コントローラー: ユーザーの入力を受け取り、適切なユースケースを呼び出します。ユーザーインターフェースとのやり取りを担当します。
- ゲートウェイ: 外部リソース（データベース、外部APIなど）との通信を担当します。データの永続化や外部リソースへのアクセスを隠蔽し、ドメイン層やアプリケーション層に独立性を提供します。

これらのコンポーネントは、依存関係のルールに従って接続されます。すなわち、より内側の層（ドメイン層）がより外側の層（アプリケーション層、インターフェースアダプタ層）に依存しないようにします。そのため、変更が生じた場合でも、内側の層は変更を受けずに維持できます。