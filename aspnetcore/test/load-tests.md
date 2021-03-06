---
title: ASP.NET Core の負荷/ストレステスト
author: Jeremy-Meng
description: ロードテストと ASP.NET Core アプリのストレステストを行うための、いくつかの注目すべきツールとアプローチについて説明します。
ms.author: riande
ms.custom: mvc
ms.date: 4/05/2019
uid: test/loadtests
ms.openlocfilehash: 1fd77a767fb53b9276081dd712e13108094a0382
ms.sourcegitcommit: cb6015f737b6a93127016ab0f21b58e34b624ff3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "77004293"
---
# <a name="aspnet-core-loadstress-testing"></a>ASP.NET Core の負荷/ストレステスト

ロードテストとストレステストは、web アプリのパフォーマンスと拡張性を確保するために重要です。 これらの目標は、よく似たテストを共有している場合でも異なります。

**ロードテスト** – 応答の目標値を満たしながら、特定のシナリオでアプリが指定された負荷のユーザーを処理できるかどうかをテストします。 アプリは通常の状態で実行します。

**ストレステスト** &ndash; 多くの場合、長時間、極端な条件下でアプリの安定性をテストします。 テストでは、アプリの負荷を急増させたり徐々に増加させるようにユーザーの負荷を高くします。または、アプリのコンピューティングリソースを制限します。

ストレステストは、ストレスのかかったアプリが障害から回復し、正常に期待通りの動作に戻ることができるかどうかを判断します。 ストレスがかかったアプリは、通常の状態で実行されません。

Visual studio 2019 は、ロードテスト機能を備えた最新バージョンの Visual Studio です。 今後ロードテストツールが必要なお客様には、Apache JMeter、Akamai CloudTest、BlazeMeter などの別のツールをお勧めします。 詳細については、「 [Visual Studio 2019 リリースノート](/visualstudio/releases/2019/release-notes-v16.0#test-tools)」を参照してください。

## <a name="visual-studio-tools"></a>Visual Studio ツール

ユーザーは Visual Studio を使用して、web パフォーマンステストとロードテストを作成、開発、およびデバッグすることができます。 Web ブラウザーでアクションを記録することによって、テストを作成するためのオプションを使用できます。

Visual Studio 2017 を使用してロードテストプロジェクトを作成、構成、および実行する方法については、「[クイックスタート: ロードテストプロジェクトを作成](/visualstudio/test/quickstart-create-a-load-test-project?view=vs-2017)する」を参照してください。

ロードテストは、オンプレミスで実行するように構成することも、Azure DevOps を使用してクラウドで実行するように構成することもできます。

## <a name="third-party-tools"></a>サードパーティ製のツール

次の一覧には、さまざまな機能セットを備えたサードパーティの web パフォーマンスツールが含まれています。

* [Apache JMeter](https://jmeter.apache.org/)
* [ApacheBench (ab)](https://httpd.apache.org/docs/2.4/programs/ab.html)
* [Gatling](https://gatling.io/)
* [k6](https://k6.io)
* [Locust](https://locust.io/)
* [West Wind WebSurge](https://websurge.west-wind.com/)
* [Netling](https://github.com/hallatore/Netling)
* [Vegeta](https://github.com/tsenart/vegeta)

