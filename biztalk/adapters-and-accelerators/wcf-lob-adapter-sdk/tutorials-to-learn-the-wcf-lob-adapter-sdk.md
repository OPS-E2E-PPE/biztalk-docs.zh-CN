---
title: "教程以了解 WCF LOB 适配器 SDK |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99002b01-da8a-483e-ada3-1ffbe9cd7357
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3efc47a5df445e18e4a78a005c31791fe1f1fa24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorials-to-learn-the-wcf-lob-adapter-sdk"></a>若要了解 WCF LOB 适配器 SDK 的教程
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]教程包含有关如何使用信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]开发功能丰富线业务适配器以便于您的企业中企业应用程序集成。 通过使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，可由任何应用程序可以使用 WCF 绑定使用的操作和你公开的数据包括[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
 本教程包含围绕一组预定义的操作的简单示例。 不需要企业系统可用于完成这些教程的实际行。 但是，这些教程中提供的详细信息可应用于你适配器的开发需求中,，从了解元数据来编写出站的处理程序和更高版本。  

> [!TIP]
> 已完成的 Echo 适配器是在你 BizTalk 安装文件附带`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`或`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`。
  
 使用以下教程以了解如何使用的关键部分[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:  
  
-   [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。 提供有关创建适配器，公开从一组预定义的方法，后者将作为企业系统的行的字符串操作的分步说明。 适配器提供了许多常用的处理程序中实现[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括搜索、 浏览、 入站和出站操作。 在成功完成本教程中，你将具有的功能的适配器。  
  
-   [教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)。 提供使用 Echo 适配器开发中的分步指导[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)从.NET 项目。 将添加到新项目中，适配器服务引用，并提供代码来测试 Echo 适配器的入站和出站操作。  
  
-   [教程 3： 承载在 IIS 中的 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)。 提供承载 Echo 适配器开发中的分步指导[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)Internet 信息服务 (IIS) 中处理。 你还将使用 svcutil.exe （ServiceModel 元数据实用工具） 创建简单的客户端应用程序使用托管适配器 EchoString 操作。  
  
 这些教程提供了了解的一些关键功能的结构化的方法[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 它们可以已完成，但不知道[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]或[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。 但是，你将了解详细了解适配器设计背后的概念并了解如何适配器设计可帮助实现过程中如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 有关详细信息，请参阅：  
  
-   [常见的开发人员任务 wcf LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/common-developer-tasks-for-the-wcf-lob-adapter-sdk.md)  
  
-   [WCF LOB 适配器 SDK 的关键组成部分](../../adapters-and-accelerators/wcf-lob-adapter-sdk/key-components-of-the-wcf-lob-adapter-sdk.md)  
  
 在开始这些教程之前，应查看中的要求[在开始本教程之前](../../core/before-you-begin-the-tutorial.md)。  
  
 
## <a name="in-this-section"></a>本节内容  
  
-   [在开始本教程之前](../../core/before-you-begin-the-tutorial.md)  
  
-   [教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)  
  
-   [教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)  
  
-   [教程 3： 承载在 IIS 中的 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 入门](../../core/getting-started-with-biztalk-server.md)