---
title: Microsoft Windows Communication Foundation 行业务线适配器 SDK 文档 |Microsoft Docs
description: 快速链接来安装、 入门、 规划和设计、 开发，和故障排除 WCF LOB 适配器 SDK 在 BizTalk Server 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2b098c-ef41-4cc0-8063-1fd043f1176f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dbfd4454e2380c44b2ccf03adb61cd2afa84fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363484"
---
# <a name="microsoft-windows-communication-foundation-line-of-business-adapter-sdk-documentation"></a>Microsoft Windows Communication Foundation 行业务线适配器 SDK 文档
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档包含如何帮助您开发、 部署和使用适配器创建与资源[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  

## <a name="about-the-sdk"></a>有关 SDK  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是一组的运行时引擎和工具，可帮助适配器开发人员使用 WCF 创建面向服务的接口连接到现有的 LOB 系统。 SDK 的目标是实现统一开发可重用、 面向元数据的、 基于 WCF 的适配器，使企业应用程序、 数据库和消息传送平台将与每个其他进行集成。  
  
 此基于 WCF 的 SDK 为 WCF 绑定呈现到 LOB 系统的适配器。 有关适配器的使用者，适配器可以访问类似于典型的 WCF 服务;使用者无需学习新的编程模型。 可以包括自定义.NET 应用程序的多个.NET 应用程序中重复使用相同的适配器开发[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，SharePoint 和 Microsoft SQL Server Integration Services (SSIS) 通过适配器开发 – 提供 ADO.NET 填充程序。 此外，适配器还提供元数据浏览、 搜索和检索这样的功能。适配器使用者可以有选择地生成反映 LOB 系统的实时类型建模的 WCF 约定。  
 
## <a name="readme"></a>自述文件
![社区资源图标](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "社区")[自述文件和隐私](../../adapters-and-accelerators/wcf-lob-adapter-sdk/readme-and-privacy-in-the-wcf-lob-adapter-sdk.md)介绍 SDK 随附的组件，还将介绍隐私选项。 

## <a name="install"></a>安装
![入门图标](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [安装 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/install-the-wcf-lob-adapter-sdk.md)列出了安装和卸载 SDK、 删除自定义适配器和执行无提示的步骤安装。 

## <a name="get-started"></a>入门
![入门图标](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [开始使用 WCF LOB 适配器 SDK 与](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)包括一些有用的信息的用户不熟悉[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，包括概念读取和一些教程。 
  
## <a name="plan-and-design"></a>规划和设计 
![适配器体系结构图标](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [规划和设计适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)描述何时使用适配器、 通道或服务。 请参阅有关受支持的消息传递模式，设计一个 URI、 了解事务和的详细信息。

## <a name="develop-and-create"></a>开发和创建
![适配器开发图标](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [开发或创建您的适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk.md)列出了一些最佳做法，提供有关的指导版本控制、 身份验证和的详细信息。

## <a name="gac-and-deploy"></a>GAC 和部署
![适配器示例图标](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a")创建您的适配器后下, 一步是将其添加到 gac 中，更新 machine.config，并创建部署包。 [部署适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-adapter-using-the-wcf-lob-adapter-sdk.md)包括此信息。

## <a name="troubleshoot"></a>故障排除
![适配器故障排除图标](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [疑难解答适配器使用 WCF LOB 适配器 SDK 创建](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)列出了启用跟踪，请使用性能的步骤计数器和生成的 WSDL。

