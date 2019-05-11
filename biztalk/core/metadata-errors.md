---
title: 元数据错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7699aa162044e13b5f3176e38cf858a5268e25f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324953"
---
# <a name="metadata-errors"></a>元数据错误
诊断和解决 WCF 元数据错误的信息。  
  
## <a name="error-consuming-wcf-service-metadata"></a>使用 WCF 服务元数据时出错

|                 |                                   错误详细信息                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                        使用 WCF 服务元数据时出错                        |
  
### <a name="explanation"></a>解释  
 此错误表示元数据存储服务未提供或无效。  
  
### <a name="user-action"></a>用户操作  
 更正服务元数据，然后尝试使用 （如果您拥有要尝试使用的 WCF 服务）。 转到服务配置编辑器 (**svcConfigEditor.exe**) 并对配置文件进行更改。  否则，请联系服务提供程序

## <a name="failed-to-get-metadata"></a>无法获取元数据

|                 |                                   错误详细信息                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                          未能获取从元数据"{0}                          |
  
## <a name="explanation"></a>解释  
 此错误表明该服务的元数据不可用。  
  
## <a name="user-action"></a>用户操作  
 启用服务的元数据并再次运行使用向导（如果您具有要尝试使用的 WCF 服务）。 否则，请与服务提供商联系。