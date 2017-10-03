---
title: "教程 1： 从 SharePoint 站点上的 SAP 系统提供数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdc3ea5e41600aebcef1fda933735c418dec78c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a>教程 1： 从 SharePoint 站点上的 SAP 系统提供数据
本教程提供了详细的说明[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft Office SharePoint Server，在 SharePoint 门户网站上显示从 SAP 系统的业务数据。 若要演示如何使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Office SharePoint Server，考虑两个最常见的实体中任何业务： 客户和销售订单。 在此示例中，在使用的 Office SharePoint Server 中创建的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以执行以下操作：  
  
-   从 SAP 系统基于搜索字符串中检索一个客户列表。  
  
-   客户，从列表和存在的详细信息中选择一个客户。  
  
-   检索所选客户的销售订单。  
  
 若要从某个 SAP 系统中提取客户数据，该示例，请使用 SD_RFC_CUSTOMER_GET RFC。 若要提取特定客户的销售订单有关的信息，它使用 BAPI_SALESORDER_GETLIST RFC。  
  
> [!NOTE]
>  某些版本的 SAP 系统公开而不是 SD_RFC_CUSTOMER_GET RFC_CUSTOMER_GET RFC。  
  
> [!NOTE]
>  本教程之前，确保已安装使用的所有先决条件[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Office SharePoint Server。 有关先决条件的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南，通常安装在 c: / Program 文件/Microsoft  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /文档。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 发布的 SAP 项目作为一个 WCF 服务](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [步骤 3： 创建 SharePoint 应用程序从 SAP 检索数据](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [步骤 4： 测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a>另请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)