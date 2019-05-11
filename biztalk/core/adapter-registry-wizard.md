---
title: 适配器注册向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a103dd40bfce3c4207d1d37eae0afd93fb868f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361261"
---
# <a name="adapter-registry-wizard"></a>适配器注册向导
适配器注册向导用于创建所需配置和注册自定义适配器的注册表文件。  

## <a name="location-in-sdk"></a>在 SDK 中的位置  
 *\<安装路径\>* \SDK\Utilities\AdapterRegistryWizard\  

## <a name="to-run-this-utility"></a>若要运行此实用程序  
 通过运行 AdapterRegistryWizard.exe 可执行文件启动向导。 向导中的页面提示您有关您的适配器和它所支持的属性信息。 各适配器注册向导页所述后面的部分。  

### <a name="generic-adapter-properties-page"></a>泛型适配器属性页  
 泛型适配器属性页用于指定适配器的属性。  


|                              使用此选项                              |                                                                                           执行的操作                                                                                           |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                     **传输适配器类型**                     |                                                                                   指定的适配器类型。                                                                                    |
|                       **属性命名空间**                       | 指定适配器命名空间。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此命名空间中的消息上下文上存储特定于适配器的属性。 |
| **适配器可以接收消息并将其提交到 BizTalk Server** |                                  标识适配器支持的通信模式。 用于计算适配器的约束注册表条目。                                   |
|         **适配器可以从 BizTalk Server 发送消息**          |                                  标识适配器支持的通信模式。 用于计算适配器的约束注册表条目。                                   |

### <a name="inbound-part-page"></a>入站的部件页  
 使用入站部分页可以指定您的适配器的入站接收逻辑。  

|使用此选项|执行的操作|  
|--------------|----------------|  
|**“浏览”**|选择实现您的适配器的入站接收逻辑的程序集。 在下拉列表中显示此程序集公开的公共类型的列表。 选择实现此适配器从下拉列表的入站的逻辑的指定程序集内的类型。|  
|**适配器支持请求-响应协议**|指定您的适配器的接收功能。 用于计算适配器的约束注册表条目。|  
|**适配器是独立 （不同进程中承载）**|指定您的适配器的接收功能。 用于计算适配器的约束注册表条目。|  

### <a name="outbound-part-page"></a>出站部件页  
 使用出站部分页可以指定您的适配器的出站接收逻辑。  

|使用此选项|执行的操作|  
|--------------|----------------|  
|**“浏览”**|选择实现您的适配器的出站接收逻辑的程序集。 在下拉列表中将显示此程序集公开的公共类型的列表。 为实现此适配器从下拉列表中的出站逻辑的指定程序集选择的类型。 您还必须输入用于标识此适配器使用的协议的别名的逗号分隔列表 (例如，提交: / /)。|  
|**适配器支持要求-响应协议**|确定您的适配器的传输性能。 这些值用于计算适配器的约束注册表条目。|  

### <a name="adapter-management-page"></a>适配器管理页  
 使用适配器管理页可以指定您的适配器的设计时管理逻辑。  

|使用此选项|执行的操作|  
|--------------|----------------|  
|**“浏览”**|选择实现您的适配器的设计时适配器管理逻辑的程序集。 在下拉列表中将显示此程序集公开的公共类型的列表。 指定实现适配器管理逻辑，从下拉列表中此适配器的程序集选择的类型。|  

### <a name="output-file-name"></a>输出文件的名称  
 使用输出文件名称页可以指定输出文件的名称和位置。  

|使用此选项|执行的操作|  
|--------------|----------------|  
|**“浏览”**|选择输出文件的名称和位置。 适配器注册表写入此文件。|  

## <a name="remarks"></a>备注  
 适配器注册向导实用程序填充企业单一登录 (SSO) 配置存储属性的默认值。 如果您的适配器不使用框架提供的适配器处理程序和位置适配器属性的标准属性页，则必须编辑注册表文件手动来修改这些值。 有关这些设置的详细信息，请参阅"注册的 SSO 配置存储的适配器属性"主题中[注册适配器](../core/registering-an-adapter.md)。  

## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)   
 [注册适配器](../core/registering-an-adapter.md)