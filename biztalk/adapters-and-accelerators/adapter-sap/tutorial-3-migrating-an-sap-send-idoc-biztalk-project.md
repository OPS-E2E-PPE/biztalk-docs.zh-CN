---
title: 教程 3： 迁移 SAP 发送 IDOC BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9aaf4fae9afaad2900f0354aec9f1eeb3f3de0ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966446"
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a>教程 3： 迁移 SAP 发送 IDOC BizTalk 项目
SAP 适配器随 Microsoft BizTalk Server 的以前版本不同于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在许多方面，包括：  
  
- 创建 BizTalk 项目的设计时体验。  
  
- 元数据检索体验。  
  
- 架构文件的名称和命名空间。  
  
- 数据类型映射。  
  
- 可以使用适配器执行的操作。  
  
- 在 BizTalk Server 管理控制台中的物理端口配置。  
  
  在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 SAP 适配器的上一步版本](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)。  
  
  但是，可以创建使用以前版本的适配器的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
  本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。  
  
> [!NOTE]
>  本教程中，为了简洁起见，在以前版本的 SAP 适配器称为 vPrev SAP 适配器。 同样，使用 vPrev SAP 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。  
  
## <a name="sample-used-for-the-tutorial"></a>本教程使用示例  
 基于本教程演示如何迁移将 IDOC 发送到 SAP 系统的 vPrev BizTalk 项目的示例 (SendIDOC_Migration)。 使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>必要條件  
  
-   必须有一个 vPrev BizTalk 项目。 本教程涉及到将 BOMDOC IDOC 发送到 SAP 系统的 BizTalk 项目。  
  
-   您必须具有平面文件 BOMDOC IDOC 发送到 SAP 系统使用 vPrev SAP 适配器。 对于本教程提供的示例包含此平面文件 IDOC。  
  
-   [创建强名称密钥文件并了解相关工具](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前版本的适配器  
 是的关键组成部分 vPrev BizTalk 项目以将 IDOC 发送：  
  
-   **BizTalk 业务流程**。 这是一个简单的业务流程从文件位置提取平面文件 IDOC 并发送到 SAP 系统使用 SAP IDOC 发送端口。 BizTalk 项目包含平面文件拆装器将平面文件 IDOC 转换为 XML，以便可以在业务流程中使用它。 XML IDOC 供的 vPrev SAP 发送端口之前，它将转换回使用平面文件组装器平面文件 IDOC。  
  
-   **你想要将发送到 SAP 系统的 IDOC 的架构**。 对于本教程中，您需要将 BOMDOC01 IDOC 发送到 SAP 系统的 BizTalk 项目。 生成 IDOC 的架构是 BOMDOC01.xsd。 此架构是使用 vPrev SAP 适配器生成的。  
  
-   **平面文件 IDOC**。 这是发送到 SAP 系统的平面文件 IDOC。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>使用以前版本的适配器如何迁移 BizTalk 项目创建  
 此迁移教程的目的是使您能够将平面文件 IDOC 发送到 SAP 系统为 vPrev SAP 适配器使用而不发送端口的 Wcf-custom 发送端口。 在了解哪些设置所需的 Wcf-custom 发送端口之前, 您首先必须了解哪些物理端口所需的 vPrev 发送 IDOC 的业务流程：  
  
- File 接收端口提取平面文件 IDOC。 此端口使用平面文件拆装器管道的 BizTalk 应用程序，可将平面文件转换为符合架构 (BOMDOC01.xsd) 使用 vPrev SAP 适配器生成的 XML。  
  
- VPrev SAP 发送将平面文件 IDOC 发送到 SAP 系统的端口。 在发送前平面文件，该端口使用平面文件组装器将 XML IDOC 平面文件 IDOC 转换。  
  
  若要迁移现有 vPrev BizTalk 项目，你不必更改文件接收端口提取平面文件 IDOC 并将平面文件 IDOC 转换为 XML 使用平面文件拆装器。 只需使用正确的配置设置来配置新的 WCF 自定义发送端口。 本教程演示如何配置 Wcf-custom 发送端口以将 Idoc 发送到 SAP 系统使用基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：生成和部署 vPrev BizTalk 项目以发送 IDOC](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [步骤 2：配置 WCF 自定义单向发送端口](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [步骤 3：测试已迁移的应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a>请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)