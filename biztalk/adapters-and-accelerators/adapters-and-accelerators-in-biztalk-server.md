---
title: 适配器和 BizTalk Server 中的加速器 |Microsoft Docs
description: 所有适配器和加速器在 BizTalk 中，包括内置适配器、 BAP、 HL7、 Swift、 RosettaNet、 FileAct 和交互的概述
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7f26a1-e47b-4323-b9f0-58842c55a6f8
ms.author: mandia
ms.openlocfilehash: 5d1d43e53a385f8b2116845fac0a4303f4ec388d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367346"
---
# <a name="adapters-and-accelerators-in-biztalk-server"></a>适配器和 BizTalk Server 中的加速器
 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 包括不同的适配器和加速器，以便创建接收数据，并将数据发送到不同的服务和 LOB 系统应用程序。 
 
本部分介绍不同的适配器和加速器适用于[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。 

## <a name="out-of-the-box-adapters"></a>开箱适配器
在安装 BizTalk Server 时，您还会安装可供使用的内置适配器。 一些这些适配器包括文件、 FTP、 MQ Series、 服务总线、 逻辑应用、 POP3、 SharePoint 和的详细信息。

**[使用适配器](../core/using-adapters.md)列出了所有这些问题，并还演示如何使用每个适配器。**
 
## <a name="biztalk-adapter-pack"></a>BizTalk 适配器包
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并提供了基于 WCF 的适配器，以连接您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Oracle、 SAP、 Siebel 和 SQL Server。 此外可以创建使用你自己的基于 WCF 的适配器[!INCLUDE[afproductnameshort_md](../includes/afproductnameshort-md.md)]。 

**请参阅[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)来安装和配置这些适配器，单步执行教程和方案中，创建应用程序使用不同的适配器，并获取清楚地了解如何基于 WCF 的服务处理消息。**

## <a name="adapters-for-enterprise-applications"></a>用于企业应用程序适配器
这些适配器所含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 使用这些适配器将使用 JD Edwards EnterpriseOne，JD Edwards OneWorld 的 BizTalk Server、 PeopleSoft Enterprise、 TIBCO Enterprise Message Service 和 TIBCO Rendezvous 连接。

**请参阅[企业应用程序的 BizTalk 适配器](biztalk-adapters-for-enterprise-applications.md)若要安装和配置这些适配器，单步执行教程和方案中，创建使用不同的适配器，以及更多的应用程序。** 


## <a name="fileact-and-interact"></a>FileAct 和交互
[!INCLUDE[swift_adapter_md](../includes/swift-adapter-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并提供之间的连接你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和社会全球 Interbank 金融电信 (SWIFT) Secure IP Network (SIPN) 有关。 

FileAct 适配器提供了安全且可靠的文件，并对这些文件相关的信息的交换。 

InterAct 适配器提供了安全且可靠的单个结构化的财务消息的交换。 

**请参阅[FileAct 和 InterAct](../adapters-and-accelerators/fileact-interact/microsoft-biztalk-server-fileact-and-interact-adapters-documentation.md)来安装和配置这些适配器，单步执行一些教程和方案，并充分了解体系结构。** 

## <a name="hl7"></a>HL7

[!INCLUDE[btaBTAHL7NoNumber_md](../includes/btabtahl7nonumber-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并提供之间的连接在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和卫生保健计算机应用程序基于运行状况级别 7 (HL7) 标准。

**请参阅[HL7](../adapters-and-accelerators/accelerator-hl7/microsoft-biztalk-accelerator-for-hl7-documentation.md)来安装和配置的适配器，单步执行几个教程和方案，了解该适配器的工作原理，并使用不同的功能，包括架构、 确认、 批处理、 验证和的详细信息。**

## <a name="rosettanet"></a>RosettaNet
BizTalk Accelerator for RosettaNet (BTARN) 是包含在 BizTalk Server，并简化了开发和部署的 RosettaNet 基于标准的集成解决方案。 BTARN 支持 RosettaNet 实现框架 (RNIF);这是一种开放式网络应用程序框架，使业务合作伙伴能够协同运行 RosettaNet 合作伙伴接口流程 (Pip)。 

**请参阅[RosettaNet](../adapters-and-accelerators/accelerator-rosettanet/microsoft-biztalk-accelerator-for-rosettanet-documentation.md)若要了解有关此加速器，并使用与 BizTalk Server 解决方案的详细信息。** 

## <a name="swift"></a>SWIFT
[!INCLUDE[btaA4SWIFTNoVersion_md](../includes/btaa4swiftnoversion-md.md)]附带[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并提供之间的连接在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]和社会的全球 Interbank 金融电信 (SWIFT) 消息格式。

使用与适配器[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，客户、 合作伙伴和系统集成商可以简化开发、 部署和支持的核心金融服务应用程序基础结构和业务流程的集成解决方案。

**请参阅[SWIFT](../adapters-and-accelerators/accelerator-swift/microsoft-biztalk-accelerator-for-swift-documentation.md)若要安装和配置该适配器，单步执行一些教程，并使用消息修复、 FIN 响应和 FRR 项目和的详细信息。**

## <a name="get-some-help"></a>获取帮助 
获取一些帮助，并帮助中的其他人[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]论坛[ http://go.microsoft.com/fwlink/p/?LinkId=87695 ](http://go.microsoft.com/fwlink/p/?LinkId=87695)。