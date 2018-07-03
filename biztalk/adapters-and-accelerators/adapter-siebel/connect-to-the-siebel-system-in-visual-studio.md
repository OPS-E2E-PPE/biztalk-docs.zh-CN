---
title: 连接到 Visual Studio 中的 Siebel 系统 |Microsoft Docs
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
ms.openlocfilehash: 064382776201ec6772cc4864c153731ab8c11989
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999734"
---
# <a name="connect-to-the-siebel-system-in-visual-studio"></a>连接到 Visual Studio 中的 Siebel 系统
本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 现已推出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装。 您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用开发解决方案的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 Siebel 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 现已推出[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]项目并作为的一部分安装[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装。 您使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用开发解决方案的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 Siebel 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。  
  
  > [!NOTE]
  >  因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开为 WCF 自定义绑定和 BizTalk 适配器，可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]从要连接到 Siebel 系统的 BizTalk 项目。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** 是在非 BizTalk 编程项目中可用。 您使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]开发使用 WCF 服务模型的解决方案时生成 WCF 客户端类或 WCF 服务回调接口。 有关使用 WCF 服务模型开发解决方案的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。  
  
  若要使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，您必须首先连接到 Siebel 系统。 所有三个方法所显示的对话框，您可以通过它来配置通过设置以下连接：  
  
- **连接参数**。 这些是用于生成连接 URI 名称如 Siebel 企业服务器的参数。  
  
- **用于 Siebel 系统的用户名称密码凭据**。 使用这些上进行身份验证您的 Siebel 系统建立连接。 必须指定用户名和密码。  
  
- **绑定属性**。 绑定属性是可选的是否指定主要取决于是否面向需要设置特定的绑定属性的操作。  
  
  在最低限度上，配置到 Siebel 系统连接时你只需指定绑定属性和连接参数，需要建立连接并会影响返回的元数据的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]操作您想要为目标。 但是，您还可能想要指定任何其他绑定属性和连接参数，将在运行时使用的值。 这是因为：  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]从绑定属性和连接参数，指定当配置连接并将此文件添加到你的项目创建的 BizTalk 端口绑定文件。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]创建 app.config 文件中的绑定属性和指定当配置连接并在项目目录中添加此文件的连接属性。  
  
 
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中获取 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)