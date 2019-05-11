---
title: 消息充实示例工作原理 |Microsoft Docs
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
ms.openlocfilehash: 2d304fbcaaf13b6f2b00b6de0e4813f3084203d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279100"
---
# <a name="how-the-message-enrichment-sample-works"></a><span data-ttu-id="f5a3e-102">消息充实示例工作原理</span><span class="sxs-lookup"><span data-stu-id="f5a3e-102">How the Message Enrichment Sample Works</span></span>
 <span data-ttu-id="f5a3e-103">消息收集示例演示就可以封装通用的可重用服务的集成模式。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-103">The Message Enrichment sample demonstrates that it is possible to encapsulate an integration pattern as a generic reusable service.</span></span> <span data-ttu-id="f5a3e-104">在这种情况下，该示例实现内容扩充器添加模式。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-104">In this case the sample implements the Content Enricher pattern.</span></span> <span data-ttu-id="f5a3e-105">内容扩充器添加模式通常涉及使用一个转换，以便准备的消息以发送给外部服务按顺序查找信息和另一个转换以将响应合并到新的消息，其中还包含中的数据原始消息。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-105">The Content Enricher pattern generally involves using a transform to prepare a message for transmission to an external service in order to lookup information, and then another transform to incorporate the response into a new message which also contains data from the original message.</span></span> <span data-ttu-id="f5a3e-106">为了采用一般形式实现的模式，消息收集示例提供了一种基于业务流程的路线服务，可以使用最多两个冲突解决程序来配置使用来自外部源的信息的消息的扩充。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-106">In order to implement the pattern in a generic fashion, the Message Enrichment sample provides an orchestration-based itinerary service that can use up to two resolvers to configure enrichment of a message using information from an external source.</span></span>
  
 <span data-ttu-id="f5a3e-107">第一个冲突解决程序必须返回路由的信息;它还可以返回转换在其旁边的信息。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-107">The first resolver must return routing information; it can also return transform information alongside it.</span></span> <span data-ttu-id="f5a3e-108">如果指定，转换前应用了传入消息路由到由解析程序指定的位置。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-108">If specified, the transform is applied to the incoming message before being routed to the location specified by the resolver.</span></span> <span data-ttu-id="f5a3e-109">在提供的示例路线，WCF 自定义适配器提供程序用于执行名为 GetOrderDetails GlobalBankESB 数据库中的 SQL 存储过程，并返回结果。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-109">In the provided sample itinerary, the WCF-Custom adapter provider is used to execute a SQL stored procedure within the GlobalBankESB database named GetOrderDetails and return the result.</span></span>  
  
 <span data-ttu-id="f5a3e-110">（可选） 可以包含第二个冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-110">Optionally, a second resolver can be included.</span></span> <span data-ttu-id="f5a3e-111">如果提供，第二个冲突解决程序必须包含转换的信息。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-111">If provided, the second resolver must include transformation information.</span></span> <span data-ttu-id="f5a3e-112">将给定此转换，原始消息和返回任何数据源进行联络，作为输入的结果。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-112">This transform will be given the original message and the result, returned by whichever data source was contacted, as input.</span></span> <span data-ttu-id="f5a3e-113">在示例路线被引用使用循环 functoid 的表来提取原始消息和存储过程的结果中的信息并将其包含在生成的 InventoryOrder 消息的映射。</span><span class="sxs-lookup"><span data-stu-id="f5a3e-113">In the sample itinerary, a map is referenced that uses a table looping functoid to pull information out of the original message and the result of the stored procedure and include it inside the resulting InventoryOrder message.</span></span>
