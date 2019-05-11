---
title: 连接到 Visual Studio 中的 SAP 系统 |Microsoft Docs
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
ms.openlocfilehash: 78aa28705c552ed037758247b2cb829bf8c9c2fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373636"
---
# <a name="connect-to-the-sap-system-in-visual-studio"></a>连接到 Visual Studio 中的 SAP 系统
本部分提供有关如何使用信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 是在 BizTalk Server 项目中可用。 您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 是在 BizTalk Server 项目中可用。 您使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
  > [!NOTE]
  >  因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开为 WCF 自定义绑定和 BizTalk 适配器，可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从要连接到 SAP 系统的 BizTalk 项目。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 是在非 BizTalk 编程项目中可用。 您使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]开发使用 WCF 服务模型的解决方案时生成 WCF 客户端类或 WCF 服务回调接口。 有关使用 WCF 服务模型开发解决方案的详细信息，请参阅[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)。  
  
  若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]您必须首先连接到 SAP 系统。 所有三个用户界面所显示的对话框，您可以通过它来配置通过设置以下连接：  
  
- **连接参数**。 这些是参数，用于构建连接 URI，例如应用程序服务器主机或消息服务器主机，以及客户端 id。  
  
- **SAP 系统的用户名密码凭据**。 使用这些上进行身份验证您的 SAP 系统时建立的连接。 必须指定用户名和密码。  
  
- **绑定属性**。 绑定属性是可选的是否指定主要取决于是否面向需要设置特定的绑定属性的操作。 例如，对于 ReceiveIdoc 操作必须设置**ReceiveIdocFormat**属性绑定到字符串。 有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
  在最低限度上，配置到 SAP 系统中，连接时你只需指定绑定属性和连接参数，需要建立连接并会影响返回的元数据的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作您想要为目标。 但是，您还可能想要指定任何其他绑定属性和连接参数，将在运行时使用的值。 这是因为：  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和连接参数，指定当配置连接并将此文件添加到你的项目创建的 BizTalk 端口绑定文件。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 app.config 文件中的绑定属性和指定当配置连接并在项目目录中添加此文件的连接属性。  
  

  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中获取 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)