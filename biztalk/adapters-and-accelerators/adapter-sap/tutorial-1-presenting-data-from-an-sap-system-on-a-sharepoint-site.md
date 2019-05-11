---
title: 教程 1:从 SharePoint 站点上的 SAP 系统提供的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5365f75982677124e8cd529ffa78b76c66dd2358
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372392"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a>教程 1:从 SharePoint 站点上的 SAP 系统提供的数据
本教程提供了详细的说明[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Microsoft Office SharePoint Server 在 SharePoint 门户网站上显示从 SAP 系统的业务数据。 若要演示如何使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Office SharePoint Server，在任何企业中考虑两个最常见的实体： 客户和销售订单。 在此示例中，在使用的 Office SharePoint Server 中创建的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]来执行以下操作：  
  
- 从基于搜索字符串上的 SAP 系统中检索客户列表。  
  
- 客户从列表和存在的详细信息选择一个客户。  
  
- 检索所选客户的销售订单。  
  
  若要从 SAP 系统中提取客户数据，该示例使用 SD_RFC_CUSTOMER_GET RFC。 若要提取特定客户的销售订单有关的信息，它使用 BAPI_SALESORDER_GETLIST RFC。  
  
> [!NOTE]
>  某些版本的 SAP 系统公开而不是 SD_RFC_CUSTOMER_GET RFC_CUSTOMER_GET RFC。  
> 
> [!NOTE]
>  本教程前，请确保已安装使用的所有先决条件[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Office SharePoint Server。 有关先决条件的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南中，通常安装在 c: / Program Files/Microsoft  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /记录。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [步骤 2：为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [步骤 3：创建 SharePoint 应用程序以从 SAP 检索数据](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [步骤 4：测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a>请参阅  
 [SAP 适配器教程](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)