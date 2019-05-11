---
title: 教程 2:迁移 SAP RFC BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76eee4656808c56664f23cd216afeef5f564f9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372319"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a>教程 2:迁移 SAP RFC BizTalk 项目
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
 基于本教程演示如何将 SAP 系统中调用 RFC vPrev BizTalk 项目迁移的示例 (SAP_RFC_Migration)。 使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   必须有一个 vPrev BizTalk 项目。 本教程涉及调用 SD_RFC_CUSTOMER_GET RFC BizTalk 项目。  
  
-   您必须具有执行，以调用 SD_RFC_CUSTOMER_GET RFC 使用 vPrev SAP 适配器的请求消息。 请求消息必须符合 RFC 使用 vPrev SAP 适配器生成的架构。 对于本教程提供的示例包含此请求消息。  
  
-   [创建强名称密钥文件并了解相关工具](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前版本的适配器  
 是的关键组成部分 vPrev BizTalk 项目以调用 RFC:  
  
-   **BizTalk 业务流程**。 这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 SAP 的 SAP 系统的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。  
  
-   **你想要在 SAP 系统中调用 rfc 架构**。 本教程涉及调用 SD_RFC_CUSTOMER_GET RFC BizTalk 项目。 为 RFC 生成的架构是 SD_RFC_CUSTOMER_GET__x32003.xsd。 此架构是使用 vPrev SAP 适配器生成的。  
  
-   **请求消息**。 要调用 SD_RFC_CUSTOMER_GET RFC 的请求消息。 请求消息的架构符合 SD_RFC_CUSTOMER_GET RFC 的架构，如 vPrev SAP 适配器提供的。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>使用以前版本的适配器如何迁移 BizTalk 项目创建  
 此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev SAP 适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]的架构。  
  
 但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：  
  
- 为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 用于调用 RFC 调用使用基于 WCF 的在 RFC 使用 vPrev SAP 适配器添加到请求消息请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。  
  
- 创建 WCF 自定义 SAP 发送接收端口在 BizTalk Server 管理控制台。  
  
- 配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：修改 vPrev BizTalk 项目以调用 RFC](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [步骤 2：在 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [步骤 3：测试已迁移的应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a>请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)