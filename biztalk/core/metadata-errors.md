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
ms.openlocfilehash: 07167c2c0189c36f7b1a321d81bd0070398953e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975118"
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
 如果您拥有要尝试使用的 WCF 服务，则更正服务元数据，然后尝试使用该服务。 转到服务配置编辑器 (**svcConfigEditor.exe**) 并对配置文件进行更改。  否则，请联系服务提供商

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