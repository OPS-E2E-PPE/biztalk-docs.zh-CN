---
title: "适配器注册表向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f07ef6adc96a4f5819cd5438b4a5d24ce6fc0770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-registry-wizard"></a>适配器注册表向导
适配器注册表向导用于创建配置和注册的自定义适配器所需的注册表文件。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 *\<安装路径 >*\SDK\Utilities\AdapterRegistryWizard\  
  
## <a name="to-run-this-utility"></a>运行本实用工具  
 通过运行 AdapterRegistryWizard.exe 可执行程序启动该向导。 向导中的页面将提示您与适配器及其支持的属性有关的信息。 在后面的部分中将介绍各适配器注册向导页。  
  
### <a name="generic-adapter-properties-page"></a>“一般适配器属性”页  
 使用“一般适配器属性”页可指定适配器的属性。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**传输适配器类型**|指定适配器类型。|  
|**属性命名空间**|指定的适配器命名空间。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在此命名空间中的消息上下文上存储特定于适配器的属性。|  
|**适配器可以接收消息并将其提交给 BizTalk Server**|标识适配器支持的通信模式。 用于计算适配器的约束注册表条目。|  
|**适配器可以将消息从 BizTalk Server 发送**|标识适配器支持的通信模式。 用于计算适配器的约束注册表条目。|  
  
### <a name="inbound-part-page"></a>“入站部分”页  
 使用“入站部分”页可以指定您的适配器的入站接收逻辑。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**浏览**|选择为您的适配器实现入站接收逻辑的程序集。 在下拉列表中显示此程序集公开的公共类型的列表。 从下拉列表中选择指定程序集内实现此适配器的入站逻辑的类型。|  
|**适配器支持请求-响应协议**|指定您的适配器的接收性能。 用于计算你的适配器的约束注册表项。|  
|**适配器是独立 （承载于不同的进程）**|指定您的适配器的接收性能。 用于计算你的适配器的约束注册表项。|  
  
### <a name="outbound-part-page"></a>“出站部分”页  
 使用“出站部分”页可以指定您的适配器的出站接收逻辑。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**浏览**|选择为您的适配器实现出站接收逻辑的程序集。 此程序集公开的公共类型列表将显示在下拉列表中。 从下拉列表中选择实现此适配器的出站逻辑的指定程序集的类型。 您还必须输入用于标识此适配器使用协议的别名的逗号分隔的列表（例如 submit://）。|  
|**适配器支持请求作出响应协议**|标识您的适配器的传输性能。 这些值用于计算适配器的约束注册表条目。|  
  
### <a name="adapter-management-page"></a>“适配器管理”页  
 使用“适配器管理”页可以指定您的适配器的设计时管理逻辑。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**浏览**|选择为您的适配器实现设计时适配器管理逻辑的程序集。 此程序集公开的公用类型列表将出现在下拉列表中。 从下拉列表中选择为此适配器实现适配器管理逻辑的指定程序集类型。|  
  
### <a name="output-file-name"></a>输出文件名  
 使用“输出文件名”页可以指定输出文件名和位置。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**浏览**|选择输出文件名和位置。 适配器注册表将写入此文件。|  
  
## <a name="remarks"></a>注释  
 适配器注册向导实用程序使用默认值填充企业单一登录 (SSO) 配置存储属性。 如果您的适配器没有使用适配器框架提供的标准属性页来用于处理程序和位置适配器属性，则必须手动编辑注册表文件以修改这些值。 有关这些设置的详细信息，请参阅"注册的 SSO 配置存储区的适配器属性"主题中[注册适配器](../core/registering-an-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [SDK 中的实用程序](../core/utilities-in-the-sdk.md)   
 [注册的适配器](../core/registering-an-adapter.md)