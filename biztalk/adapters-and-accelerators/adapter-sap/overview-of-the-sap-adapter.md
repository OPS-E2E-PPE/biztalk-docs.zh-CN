---
title: SAP 适配器概述 |Microsoft Docs
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
ms.openlocfilehash: 58f6249774697e12e12ab5b85bccf6df210a5d4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981838"
---
# <a name="overview-of-the-sap-adapter"></a>SAP 适配器概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开为 WCF 服务的 SAP 系统。 适配器客户端可以通过该适配器与交换的 SOAP 消息执行 SAP 系统的操作。 适配器使用 WCF 消息并进行相应调用到 SAP 系统，以执行操作。 适配器返回到 SOAP 消息的窗体中的客户端从 SAP 系统返回的响应。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]曲面的 SAP 项目 (RFC，BAPI，IDOC) 描述的元数据结构的 SOAP 消息的 WSDL 格式。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]启用适配器客户端来检索操作的元数据，并在生成的编程项目，可以使用编程解决方案中。 有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，并[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Unicode RFC 库，librfc32u.dll，与 SAP 系统，除了使用其他支持的 Dll 进行通信。 SAP 适配器需要的 Dll 的完整列表，请参阅[BizTalk 适配器包安装指南](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap)。 可以使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以以下方式与 SAP 系统进行通信：  
  
- 通过开发 BizTalk 应用程序。 请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)有关详细信息。  
  
- 通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。 请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。
  
- 通过使用 WCF 通道模型。 请参阅[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 SAP 系统？](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [原理适配器图面上的 SAP 元数据是什么？](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [适配器支持的其他功能](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a>请参阅  
 [了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)