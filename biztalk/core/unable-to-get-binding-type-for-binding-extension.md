---
title: 无法获取绑定扩展的绑定类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15a55bc8f06465daec562624866ed41a43059a05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292790"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a>无法获取绑定扩展的绑定类型
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                        |
| 产品版本 |                                                                                    [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                    |
|    事件 ID     |                                                                                                                0                                                                                                                 |
|  事件源   |                                                                                                                0                                                                                                                 |
|    组件    |                                                                                                                0                                                                                                                 |
|  符号名称  |                                                                                                                0                                                                                                                 |
|  消息正文   | 无法获取绑定扩展的绑定类型"{0}"。 如果你的应用程序打开时，已更新 machine.config，重新启动应用程序要选取更改。 验证 machine.config 中注册绑定扩展 |

## <a name="explanation"></a>解释  
 适用于 Wcf-custom 或 Wcf-customisolated 传输的自定义绑定扩展是未正确配置。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行一个或多项：  

- 请确保**machine.config 文件**中 **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**具有\< **bindingExtensions** \>正确配置的元素。  

- 在 Windows 资源管理器，转到 **%WinDir%\Assembly**，并确保实现自定义绑定扩展的程序集已正确安装。  

- WCF 自定义适配器在 BizTalk 管理控制台中，重新启动运行 WCF 传输的主机实例。  

- 对于 Wcf-customisolated 适配器，在 IIS 管理控制台中，重新启动托管 WCF 传输的应用程序池。  

- 打开和关闭 BizTalk 管理控制台中，如果已打开  

  有关详细信息，请参阅以下资源：  

- [如何启用 WCF 适配器的 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)
