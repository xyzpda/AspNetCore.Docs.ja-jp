---
title: ASP.NET Core SignalR の概要
author: bradygaster
description: ASP.NET Core SignalR ライブラリを通じて、リアルタイムの機能をアプリに簡単に追加する方法について説明します。
monikerRange: '>= aspnetcore-2.1'
ms.author: bradyg
ms.custom: mvc
ms.date: 11/27/2019
no-loc:
- SignalR
uid: signalr/introduction
ms.openlocfilehash: 635431abf9263c2dff261aea47e6f8324061763f
ms.sourcegitcommit: 7dfe6cc8408ac6a4549c29ca57b0c67ec4baa8de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "75829284"
---
# <a name="introduction-to-aspnet-core-opno-locsignalr"></a>ASP.NET Core SignalR の概要

## <a name="what-is-opno-locsignalr"></a>新機能SignalRとは?

ASP.NET Core SignalR は、リアルタイムの web 機能をアプリに簡単に追加できるオープンソースライブラリです。 リアルタイム Web 機能は、サーバー側コードからクライアントにコンテンツを即座にプッシュすることを可能にします。

SignalRの候補として適しています。

* サーバーから頻度の高い更新を必要とするアプリ。 例えば、ゲーム、ソーシャル ネットワーク、投票、オークション、マップ、および GPS アプリです。
* ダッシュ ボードや監視アプリ。 会社のダッシュ ボード、即座に更新される販売情報、渡航に関する危険情報、が例に含まれます。
* コラボレーション アプリ。 ホワイト ボード アプリやチーム会議ソフトウェアがコラボレーション アプリの例です。
* 通知を必要とするアプリ。 ソーシャル ネットワーク、電子メール、チャット、ゲーム、渡航に関する危険情報、およびその他の多くのアプリが通知を使用します。

SignalR には、サーバー間の[リモートプロシージャ呼び出し (RPC)](https://wikipedia.org/wiki/Remote_procedure_call)を作成するための API が用意されています。 Rpc は、サーバー側 .NET Core コードからクライアントで JavaScript 関数を呼び出します。

ASP.NET Core の SignalR の機能をいくつか次に示します。

* 接続管理を自動的に処理します。
* 同時に接続されているすべてのクライアントにメッセージを送信します。 例えば、チャット ルーム。
* 特定のクライアントまたはクライアントグループにメッセージを送信します。
* トラフィックの増加の対応にスケールします。

ソースは、 [GitHub のSignalR リポジトリ](https://github.com/dotnet/AspNetCore/tree/master/src/SignalR)でホストされています。

## <a name="transports"></a>トランスポート

SignalR は、リアルタイム通信 (正常なフォールバックの順序) を処理するための次の手法をサポートしています。

* [WebSocket](https://tools.ietf.org/html/rfc7118)
* Server-Sent Events
* 長いポーリング

SignalR は、サーバーとクライアントの機能内にある最適なトランスポート方法を自動的に選択します。

## <a name="hubs"></a>ハブ

SignalR は、*ハブ*を使用してクライアントとサーバー間の通信を行います。

ハブは、相互にメソッドを呼び出すことをクライアントとサーバーに許可する、高度なパイプラインです。 SignalR は、コンピューターの境界を越えたディスパッチを自動的に処理するので、クライアントはサーバーでメソッドを呼び出すことができ、その逆も可能です。 モデル バインディングを有効にする厳密に型指定されたパラメーターを、メソッドに渡すことができます。 SignalR には、JSON に基づくテキストプロトコルと[Messagepack](https://msgpack.org/)に基づくバイナリプロトコルという2つの組み込みのハブプロトコルが用意されています。  MessagePack は一般に、JSON と比較して小さいメッセージを作成します。 MessagePack プロトコル サポートを提供するため、古いブラウザーは[XHR レベル 2](https://caniuse.com/#feat=xhr2)をサポートする必要があります。

ハブは、クライアント側メソッドのパラメーターと名前を含むメッセージを送信することによって、クライアント側のコードを呼び出します。 メソッドのパラメーターとして送信されたオブジェクトは、設定されたプロトコルを使用して逆シリアル化されます。 クライアントは、クライアント側コードのメソッド名との一致を試みます。 クライアントが一致を検出すると、逆シリアル化されたパラメーター データを渡してメソッドを呼び出します。

## <a name="additional-resources"></a>その他の技術情報

* [ASP.NET Core の SignalR の概要](xref:tutorials/signalr)
* [サポートされているプラットフォーム](xref:signalr/supported-platforms)
* [ハブ](xref:signalr/hubs)
* [JavaScript クライアント](xref:signalr/javascript-client)
