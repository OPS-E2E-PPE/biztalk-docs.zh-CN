---
title: 连接到 Visual Studio 中 Siebel 系统 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add Adapter Service Reference Plug-in
- Consume Adapter Service Add-in
- how to, connect to the Siebel System in Visual Studio
ms.assetid: 4a94bce9-fda9-4e00-b26c-08672a80e3be
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f7bacf42f90da21830d24587cc7ae6a6e042bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222341"
---
# <a name="connect-to-the-siebel-system-in-visual-studio"></a>连接到 Siebel 系统 Visual Studio 中
本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
-    **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关开发解决方案的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[开发 BizTalk 应用程序使用在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。  
  
-    **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 位于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装。 你使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关开发解决方案的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[开发 BizTalk 应用程序使用在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。  
  
    > [!NOTE]
    >  因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开 WCF 自定义绑定，而且作为 BizTalk 适配器，你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从 BizTalk 项目连接到 Siebel 系统。  
  
-    **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 在非 BizTalk 编程项目中可用。 你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端类或 WCF 服务回调接口，当你开发使用 WCF 服务模型的解决方案时。 有关开发与 WCF 服务模型的解决方案的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。  
  
 若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，您必须首先连接到 Siebel 系统。 所有三个方法所显示的对话框中，你可以通过它来配置通过设置以下连接：  
  
-   **连接参数**。 这些是用于生成连接 URI 如名称 Siebel 企业服务器的参数。  
  
-   **Siebel 系统的用户名密码凭据**。 这些凭据用于进行时进行身份验证你 Siebel 系统上建立的连接。 必须指定用户名和密码。  
  
-   **绑定属性**。 绑定属性是可选的并且是否指定主要取决于是否面向需要特定绑定来设置属性的操作。  
  
 在最低限度上，当你配置的连接到 Siebel 系统中，你只需指定绑定属性和连接参数，需要以建立连接并影响返回的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]操作你要设定为目标。 但是，你还可能想要指定用于任何其他绑定属性并将在运行时使用的连接参数的值。 这是因为：  
  
-   [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和连接参数，指定你配置的连接并将此文件添加到你的项目中创建 BizTalk 端口绑定文件。  
  
-   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]从的绑定属性和连接属性指定当你配置的连接并将此文件添加项目目录中创建的 app.config 文件。  
  
 
  
## <a name="see-also"></a>另请参阅  
 [获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)