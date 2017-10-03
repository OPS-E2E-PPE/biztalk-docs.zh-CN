---
title: "教程 2： 迁移 SAP RFC BizTalk 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80b5d53904b96267b1877310aa3480ce34a1bedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a>教程 2： 迁移 SAP RFC BizTalk 项目
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
 本教程基于演示如何将 SAP 系统中调用 RFC vPrev BizTalk 项目迁移的示例 (SAP_RFC_Migration)。 使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须有 vPrev BizTalk 项目。 本教程涉及调用 SD_RFC_CUSTOMER_GET RFC BizTalk 项目。  
  
-   你必须具有要执行调用使用 vPrev SAP 适配器 SD_RFC_CUSTOMER_GET RFC 的请求消息。 请求消息必须符合该架构的生成使用 vPrev SAP 适配器的 RFC。 本教程中提供的示例包含此请求消息。  
  
-   [创建强名称密钥文件，并了解工具](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前的版本的适配器  
 若要调用 RFC vPrev BizTalk 项目的关键组成部分是：  
  
-   **BizTalk 业务流程**。 这是简单的业务流程选取端口的文件位置，发送到 SAP 系统使用一个 SAP 请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。  
  
-   **你想要调用 SAP 系统中的 RFC 架构**。 本教程涉及调用 SD_RFC_CUSTOMER_GET RFC BizTalk 项目。 RFC 为生成的架构是 SD_RFC_CUSTOMER_GET__x32003.xsd。 使用 vPrev SAP 适配器生成此架构。  
  
-   **请求消息**。 要调用 SD_RFC_CUSTOMER_GET RFC 的请求消息。 请求消息的架构符合 SD_RFC_CUSTOMER_GET RFC 的架构，如显示 vPrev SAP 适配器。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>如何迁移 BizTalk 项目创建使用以前的版本的适配器  
 本教程中迁移的目标是使您能够发送请求消息符合架构生成的使用只能处理符合基于 WCF 的消息的 WCF 自定义端口和 vPrev SAP 适配器[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]的架构。  
  
 但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：  
  
-   为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   用于调用的调用使用基于 WCF 的 RFC 使用请求消息的 vPrev SAP 适配器的 RFC 将请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。  
  
-   创建 WCF 自定义 SAP 发送接收 BizTalk Server 管理控制台中的端口。  
  
-   配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 用于调用 RFC 修改 vPrev BizTalk 项目](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [步骤 2： 在 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [步骤 3： 测试已迁移的应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a>另请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)