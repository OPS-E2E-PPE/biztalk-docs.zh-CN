---
title: "教程 4： 迁移 SAP 接收 IDOC BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943c80e84bc192330fd870a45c0b5fb60761a33d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a>教程 4： 迁移 SAP 接收 IDOC BizTalk 项目
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
 本教程基于演示如何将某个 SAP 系统从接收平面文件 IDOC vPrev BizTalk 项目迁移的示例 (ReceiveIDOC_Migration)。 使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须有 vPrev BizTalk 项目。 本教程涉及从某个 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。  
  
-   [创建强名称密钥文件，并了解工具](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前的版本的适配器  
 若要接收 IDOC vPrev BizTalk 项目的关键组成部分是：  
  
-   **BizTalk 业务流程**。 这是一个简单包含一个 SAP 的业务流程接收平面文件 IDOC 收到某个 SAP 系统的端口。 BizTalk 项目包含平面文件反汇编程序中，将平面文件 IDOC 转换为 XML，以便可在业务流程。 XML IDOC 复制到文件位置通过文件端口之前，会将它转换为回使用平面文件汇编平面文件 IDOC。  
  
-   **你想要将发送到 SAP 系统 IDOC 架构**。 本教程涉及从 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。 为 IDOC 生成的架构是 ORDERS03.xsd。 使用 vPrev SAP 适配器生成此架构。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>如何迁移 BizTalk 项目创建使用以前的版本的适配器  
 本教程中迁移的目标是使您能够从 SAP 系统 WCF 自定义发送端口而不发送端口用于 vPrev SAP 适配器接收平面文件 IDOC。 了解哪些设置所需的 WCF 自定义发送端口之前, 必须先了解哪些物理端口是必需的 vPrev 发送 IDOC 业务流程。  
  
-   VPrev SAP 接收平面文件 IDOC 收到某个 SAP 系统的端口。 端口也将此转换为 XML IDOC 使用平面文件反汇编程序，它位于 vPrev BizTalk 应用程序的一部分。 XML IDOC 符合使用 vPrev SAP 适配器生成的架构 (ORDERS03.xsd)。  
  
-   用于复制到文件夹的 IDOC 的文件发送端口。 此端口也使用平面文件汇编器管道的 BizTalk 应用程序，可将 XML IDOC 转换为平面文件 IDOC。  
  
 若要迁移现有 vPrev BizTalk 项目，你不必更改文件发送端口，将平面文件 IDOC 复制到一个文件夹。 你只需以配置一个新 WCF 自定义接收具有正确的配置设置的端口。 本教程演示如何配置 WCF 自定义接收端口从使用基于 WCF 的 SAP 系统接收到的 Idoc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 生成并部署用于接收 IDOC vPrev BizTalk 项目](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [步骤 2： 配置 WCF 自定义单向接收端口](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [步骤 3： 测试已迁移的应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a>另请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)