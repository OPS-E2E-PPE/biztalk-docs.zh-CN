---
title: 消息扩充示例的工作原理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1188c1c9-b133-4438-b41c-ea6cffcf40fd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef516b992acbcee2936edb6341cbf1434ba4c79
ms.sourcegitcommit: 7497f6f23d7aadfa8535d0530493f8b4a2a50a0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
ms.locfileid: "22303669"
---
# <a name="how-the-message-enrichment-sample-works"></a><span data-ttu-id="ea961-102">消息扩充示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="ea961-102">How the Message Enrichment Sample Works</span></span>
 <span data-ttu-id="ea961-103">消息扩充示例演示可以封装作为泛型的可重用服务的集成模式。</span><span class="sxs-lookup"><span data-stu-id="ea961-103">The Message Enrichment sample demonstrates that it is possible to encapsulate an integration pattern as a generic reusable service.</span></span> <span data-ttu-id="ea961-104">在这种情况下，此示例实现内容 Enricher 模式。</span><span class="sxs-lookup"><span data-stu-id="ea961-104">In this case the sample implements the Content Enricher pattern.</span></span> <span data-ttu-id="ea961-105">内容 Enricher 模式通常涉及使用转换准备一条消息以发送给顺序查找信息，到外部服务，并将另一个转换以将响应合并到一条新消息还包含中的数据原始消息。</span><span class="sxs-lookup"><span data-stu-id="ea961-105">The Content Enricher pattern generally involves using a transform to prepare a message for transmission to an external service in order to lookup information, and then another transform to incorporate the response into a new message which also contains data from the original message.</span></span> <span data-ttu-id="ea961-106">为通用的方式实现的模式，消息扩充示例提供了一种可以使用最多两个冲突解决程序来配置使用从外部源的信息的消息的扩充基于业务流程的路线服务。</span><span class="sxs-lookup"><span data-stu-id="ea961-106">In order to implement the pattern in a generic fashion, the Message Enrichment sample provides an orchestration-based itinerary service that can use up to two resolvers to configure enrichment of a message using information from an external source.</span></span>
  
 <span data-ttu-id="ea961-107">第一个冲突解决程序必须返回路由信息;它还可以返回转换在其旁边的信息。</span><span class="sxs-lookup"><span data-stu-id="ea961-107">The first resolver must return routing information; it can also return transform information alongside it.</span></span> <span data-ttu-id="ea961-108">如果指定，路由之前应用到传入消息转换到由解析程序指定的位置。</span><span class="sxs-lookup"><span data-stu-id="ea961-108">If specified, the transform is applied to the incoming message before being routed to the location specified by the resolver.</span></span> <span data-ttu-id="ea961-109">在提供的示例路线，WCF 自定义适配器提供程序用于执行名为 GetOrderDetails GlobalBankESB 数据库内的一个 SQL 存储过程并返回结果。</span><span class="sxs-lookup"><span data-stu-id="ea961-109">In the provided sample itinerary, the WCF-Custom adapter provider is used to execute a SQL stored procedure within the GlobalBankESB database named GetOrderDetails and return the result.</span></span>  
  
 <span data-ttu-id="ea961-110">（可选） 可以包含第二个冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="ea961-110">Optionally, a second resolver can be included.</span></span> <span data-ttu-id="ea961-111">如果提供，第二个解析程序必须包括转换信息。</span><span class="sxs-lookup"><span data-stu-id="ea961-111">If provided, the second resolver must include transformation information.</span></span> <span data-ttu-id="ea961-112">将给定此转换，原始消息和返回任何数据源已连接，作为输入的结果。</span><span class="sxs-lookup"><span data-stu-id="ea961-112">This transform will be given the original message and the result, returned by whichever data source was contacted, as input.</span></span> <span data-ttu-id="ea961-113">在示例路线中被引用使用循环 functoid 表中提取出原始消息和存储过程的结果的信息并将其包含在生成的 InventoryOrder 消息映射。</span><span class="sxs-lookup"><span data-stu-id="ea961-113">In the sample itinerary, a map is referenced that uses a table looping functoid to pull information out of the original message and the result of the stored procedure and include it inside the resulting InventoryOrder message.</span></span>
