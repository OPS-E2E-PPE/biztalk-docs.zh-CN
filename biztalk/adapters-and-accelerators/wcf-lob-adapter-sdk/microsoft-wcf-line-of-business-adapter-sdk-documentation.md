---
title: "Microsoft Windows Communication Foundation 行的业务适配器 SDK 文档 |Microsoft 文档"
description: "快速链接来安装、 入门、 规划和设计、 开发，和故障排除 WCF LOB 适配器 SDK BizTalk Server 中"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a2b098c-ef41-4cc0-8063-1fd043f1176f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8472fb56beab8f6d86ff33bebb9171d09d503ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="microsoft-windows-communication-foundation-line-of-business-adapter-sdk-documentation"></a>Microsoft Windows Communication Foundation 行的业务适配器 SDK 文档
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档包括的资源来帮助你开发、 部署和使用与创建的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。  

## <a name="about-the-sdk"></a>有关 SDK  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是运行时引擎的集合并帮助适配器开发人员的工具创建使用 WCF 的面向服务的接口连接到现有的 LOB 系统。 该 SDK 的目标是为了便于统一开发的启用企业应用程序、 数据库和消息传送平台，以相互集成的可重用、 面向元数据的、 基于 WCF 的适配器。  
  
 此基于 WCF 的 SDK 为 WCF 绑定呈现到 LOB 系统的适配器。 适配器使用者，适配器可以访问与典型的 WCF 服务;使用者不必了解新的编程模型。 可以在包括自定义.NET 应用程序的多个.NET 应用程序中重用同一个适配器开发[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，SharePoint 和 Microsoft SQL Server Integration Services (SSIS) 通过适配器提供开发人员 – ADO.NET 填充码。 此外，该适配器提供元数据浏览、 搜索和检索功能;适配器使用者可以有选择地生成反映的 LOB 系统的实时类型建模的 WCF 协定。  
 
## <a name="readme"></a>自述文件
![社区资源图标](../../adapters-and-accelerators/adapter-oracle-database/media/community.gif "社区")[自述文件和隐私](../../adapters-and-accelerators/wcf-lob-adapter-sdk/readme-and-privacy-in-the-wcf-lob-adapter-sdk.md)介绍了在 SDK 随附的组件以及你说明了的隐私选项。 

## <a name="install"></a>Install
![快速入门图标](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [安装 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/install-the-wcf-lob-adapter-sdk.md)列出安装和卸载 SDK，请删除自定义适配器，并执行的步骤无提示安装。 

## <a name="get-started"></a>要开始
![快速入门图标](../../adapters-and-accelerators/adapter-oracle-database/media/f397b0c1-6fe1-4247-a868-9efcab4a5f55.gif "f397b0c1-6fe1-4247-a868-9efcab4a5f55") [开始使用与 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)包括用户熟悉一些有用的信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，包括概念读取和某些教程。 
  
## <a name="plan-and-design"></a>规划和设计 
![适配器体系结构图标](../../adapters-and-accelerators/adapter-oracle-database/media/4af6a1c5-948f-4bf7-bb56-4d63a47f4825.gif "4af6a1c5-948f-4bf7-bb56-4d63a47f4825") [规划和设计使用 WCF LOB 适配器 SDK 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)描述何时使用适配器、 一个通道或服务. 请参阅有关受支持的消息传递模式，设计一个 URI，了解事务和的详细信息。

## <a name="develop-and-create"></a>开发和创建
![适配器开发图标](../../adapters-and-accelerators/adapter-oracle-database/media/44af70c9-cab1-4201-9912-d115cbc7e16f.gif "44af70c9-cab1-4201-9912-d115cbc7e16f") [开发或创建使用 WCF LOB 适配器 SDK 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk.md)列出了一些最佳做法，提供有关的指导版本控制、 身份验证，和的详细信息。

## <a name="gac-and-deploy"></a>GAC 和部署
![适配器示例图标](../../adapters-and-accelerators/adapter-sap/media/2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a.gif "2e8eba6a-6ba1-431e-9e0a-f0f45e036e8a")创建适配器后下, 一步是将其添加到 gac 中，更新 machine.config，并创建部署包。 [部署使用 WCF LOB 适配器 SDK 的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-adapter-using-the-wcf-lob-adapter-sdk.md)包括此信息。

## <a name="troubleshoot"></a>故障排除
![适配器故障排除图标](../../adapters-and-accelerators/adapter-oracle-database/media/383a7392-2eb9-485d-b6a8-0187cd5c709d.gif "383a7392-2eb9-485d-b6a8-0187cd5c709d") [使用 WCF LOB 适配器 SDK 创建的故障排除适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)列表的步骤启用跟踪，使用性能计数器和生成的 WSDL。

