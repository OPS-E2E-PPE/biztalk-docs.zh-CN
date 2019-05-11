---
title: 教程 4:迁移 SAP 接收 IDOC BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bfb0205464a5c7163c3ebc61e1ee4c53139278
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372299"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a>教程 4:迁移 SAP 接收 IDOC BizTalk 项目
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
 基于本教程演示如何从 SAP 系统接收平面文件 IDOC 的 vPrev BizTalk 项目迁移的示例 (ReceiveIDOC_Migration)。 使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   必须有一个 vPrev BizTalk 项目。 本教程涉及到从 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。  
  
-   [创建强名称密钥文件并了解相关工具](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前版本的适配器  
 关键组成部分 vPrev BizTalk 项目以接收 IDOC 是：  
  
-   **BizTalk 业务流程**。 这是一个简单包含一个 SAP 的业务流程接收端口接收来自 SAP 系统的平面文件 IDOC。 BizTalk 项目包含平面文件拆装器将平面文件 IDOC 转换为 XML，以便可以在业务流程中使用它。 XML IDOC 复制到文件位置通过 file 端口之前，它将转换回使用平面文件组装器平面文件 IDOC。  
  
-   **你想要将发送到 SAP 系统的 IDOC 的架构**。 本教程涉及到从 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。 生成 IDOC 的架构是 ORDERS03.xsd。 此架构是使用 vPrev SAP 适配器生成的。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>使用以前版本的适配器如何迁移 BizTalk 项目创建  
 此迁移教程的目的是使您能够从 SAP 系统为 vPrev SAP 适配器使用而不发送端口的 Wcf-custom 发送端口接收平面文件 IDOC。 之前了解哪些设置所需的 Wcf-custom 发送端口，您首先必须了解哪些物理端口所需的 vPrev 发送 IDOC 的业务流程。  
  
- VPrev SAP 接收端口接收来自 SAP 系统的平面文件 IDOC。 端口还将此转换为 XML IDOC 使用平面文件拆装器，可作为 vPrev BizTalk 应用程序的一部分。 使用 vPrev SAP 适配器生成的架构 (ORDERS03.xsd) 符合 XML IDOC。  
  
- File 发送端口将 IDOC 复制到文件夹。 此端口还使用平面文件组装器管道的 BizTalk 应用程序，可将 XML IDOC 转换为平面文件 IDOC。  
  
  若要迁移现有 vPrev BizTalk 项目，你不必更改复制到的文件夹的平面文件 IDOC 的文件发送端口。 只需配置一个新 WCF 自定义接收端口使用正确的配置设置。 本教程演示如何配置 WCF 自定义接收端口以接收来自 SAP 系统使用基于 WCF 的 Idoc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：生成和部署 vPrev BizTalk 项目以接收 IDOC](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [步骤 2：配置 WCF 自定义单向接收端口](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [步骤 3：测试已迁移的应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a>请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)