---
title: "教程 3： 迁移 SAP 发送 IDOC BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52f8bc638d1adefe952ce055542706d11e0ca61f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a>教程 3： 迁移 SAP 发送 IDOC BizTalk 项目
SAP 适配器随 Microsoft BizTalk Server 以前版本的基于 WCF 的不同[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在许多方面，包括：  
  
-   创建 BizTalk 项目的设计时体验。  
  
-   元数据检索体验。  
  
-   架构文件名称和命名空间。  
  
-   数据类型映射。  
  
-   可以使用该适配器执行的操作。  
  
-   在 BizTalk Server 管理控制台中的物理端口配置。  
  
 在中的主题解释了这些差异[迁移 BizTalk 项目创建使用上一步版本的 SAP 适配器](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)。  
  
 但是，你可以使用以前版本的适配器创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
 本教程将说明了你应创建使用以前的版本的适配器的现有 BizTalk 项目的更改。  
  
> [!NOTE]
>  在本教程中，由于篇幅所限，以前版本的 SAP 适配器称为 vPrev SAP 适配器。 同样，使用 vPrev SAP 适配器的 BizTalk 项目将被称为 vPrev BizTalk 项目。  
  
## <a name="sample-used-for-the-tutorial"></a>使用本教程的示例  
 本教程基于演示如何迁移将 IDOC 发送到 SAP 系统的 vPrev BizTalk 项目的示例 (SendIDOC_Migration)。 使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须有 vPrev BizTalk 项目。 本教程涉及将 BOMDOC IDOC 发送到 SAP 系统的 BizTalk 项目。  
  
-   你必须具有平面文件 BOMDOC IDOC 发送到 SAP 系统使用 vPrev SAP 适配器。 本教程中提供的示例包含此平面文件 IDOC。  
  
-   [创建强名称密钥文件，并了解工具](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前的版本的适配器  
 若要发送 IDOC vPrev BizTalk 项目的关键组成部分是：  
  
-   **BizTalk 业务流程**。 这是简单的业务流程，从文件位置选取平面文件 IDOC 并将发送到 SAP 系统使用一个 SAP IDOC 发送端口。 BizTalk 项目包含平面文件反汇编程序中，将平面文件 IDOC 转换为 XML，以便可在业务流程。 XML IDOC 由 SAP 发送端口 vPrev 之前，会将它转换为回使用平面文件汇编平面文件 IDOC。  
  
-   **你想要将发送到 SAP 系统 IDOC 架构**。 对于本教程中，你需要将 BOMDOC01 IDOC 发送到 SAP 系统的 BizTalk 项目。 为 IDOC 生成的架构是 BOMDOC01.xsd。 使用 vPrev SAP 适配器生成此架构。  
  
-   **平面文件 IDOC**。 这是发送到 SAP 系统平面文件 IDOC。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>如何迁移 BizTalk 项目创建使用以前的版本的适配器  
 本教程中迁移的目标是使您能够将平面文件 IDOC 发送到 WCF 自定义发送端口而不发送端口用于 vPrev SAP 适配器 SAP 系统。 了解哪些设置所需的 WCF 自定义发送端口之前, 必须先了解哪些物理端口是必需的 vPrev 发送 IDOC 业务流程：  
  
-   文件接收选取平面文件 IDOC 的端口。 此端口使用平面文件反汇编程序管道的 BizTalk 应用程序，可将平面文件转换为符合架构 (BOMDOC01.xsd) 使用 vPrev SAP 适配器生成的 XML。  
  
-   VPrev SAP 发送将平面文件 IDOC 发送到 SAP 系统的端口。 在发送之前将平面文件，该端口使用的平面文件汇编将 XML IDOC 转换为平面文件 IDOC。  
  
 若要迁移现有 vPrev BizTalk 项目，你不必更改文件接收选取平面文件 IDOC 并将平面文件 IDOC 转换为 XML 使用平面文件反汇编程序的端口。 只需使用正确的配置设置来配置新的 WCF 自定义发送端口。 本教程演示如何配置 WCF 自定义发送端口将 Idoc 发送到使用基于 WCF 的 SAP 系统[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 生成并发送 IDOC 部署 vPrev BizTalk 项目](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [步骤 2： 配置 WCF 自定义单向发送端口](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [步骤 3： 测试已迁移的应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a>另请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)