---
title: SAP 适配器概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, overview
ms.assetid: 2d078b13-d41f-476f-bfb4-82be4d35a769
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3031bdf1317d96f64f1ea247c6f8cbf83e1688c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963027"
---
# <a name="overview-of-the-sap-adapter"></a>SAP 适配器的概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开 SAP 系统作为 WCF 服务。 适配器客户端可以通过交换 SOAP 消息与适配器执行 SAP 系统上的操作。 适配器使用 WCF 消息，并且到 SAP 系统的适当调用来执行该操作。 适配器回客户端的 SOAP 消息的形式，并将响应返回从 SAP 系统。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面元数据的 SAP 项目 (RFC，BAPI，IDOC) 描述的结构的 SOAP 消息的 WSDL 形式。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据并在编程解决方案中生成可用的编程项目。 有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Unicode RFC 库，librfc32u.dll，与 SAP 系统，除了使用其他支持 Dll 进行通信。 有关 SAP 适配器需要的 Dll 的完整列表，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南。 安装指南通常安装在\<安装驱动器：\>\Program Files\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。 你可以使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以下列方式与 SAP 系统进行通信：  
  
-   通过开发 BizTalk 应用程序。 请参阅[开发 BizTalk 服务器应用程序](../../core/developing-biztalk-server-applications.md)有关详细信息。  
  
-   通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。
  
-   通过使用 WCF 通道模型。 请参阅[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 SAP 系统？](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [原理适配器图面 SAP 元数据是什么？](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [适配器支持的其他功能](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a>另请参阅  
 [了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)