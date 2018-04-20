---
title: 连接到 Visual Studio 中的 SAP 系统 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- Add Adapter Service Reference Visual Studio Plug-in
- Consume Adapter Service BizTalk Project Add-in
ms.assetid: 5fc356b1-05e8-4235-bb04-5ef6192c5291
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20cd25c327f2081fed61e19e1571b91a0e39f556
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="connect-to-the-sap-system-in-visual-studio"></a>连接到 Visual Studio 中的 SAP 系统
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-   **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**在 BizTalk Server 项目中可用。 你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
-   **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**在 BizTalk Server 项目中可用。 你使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
    > [!NOTE]
    >  因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开 WCF 自定义绑定，而且作为 BizTalk 适配器，你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从 BizTalk 项目以连接到 SAP 系统。  
  
-   **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**在非 BizTalk 编程项目中可用。 你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端类或 WCF 服务回调接口，当你开发使用 WCF 服务模型的解决方案时。 有关开发与 WCF 服务模型的解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
 若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]必须先连接到 SAP 系统。 所有三个用户界面所显示的对话框中，你可以通过它来配置通过设置以下连接：  
  
-   **连接参数**。 这些是用于生成应用程序服务器主机或消息服务器主机等客户端 id。 连接 URI 参数  
  
-   **SAP 系统的用户名密码凭据**。 这些凭据用于进行时进行身份验证你在 SAP 系统上建立的连接。 必须指定用户名和密码。  
  
-   **绑定属性**。 绑定属性是可选的并且是否指定主要取决于是否面向需要特定绑定来设置属性的操作。 例如，对于 ReceiveIdoc 操作必须设置**ReceiveIdocFormat**将属性绑定到字符串。 有关绑定属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
 在最低限度上，配置到 SAP 系统中，连接时你只需指定绑定属性和连接参数，需要以建立连接并影响返回的元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作你要设定为目标。 但是，你还可能想要指定用于任何其他绑定属性并将在运行时使用的连接参数的值。 这是因为：  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和连接参数，指定你配置的连接并将此文件添加到你的项目中创建 BizTalk 端口绑定文件。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]从的绑定属性和连接属性指定当你配置的连接并将此文件添加项目目录中创建的 app.config 文件。  
  

  
## <a name="see-also"></a>另请参阅  
 [在 Visual Studio 中获取 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)