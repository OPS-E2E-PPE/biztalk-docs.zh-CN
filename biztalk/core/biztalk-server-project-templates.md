---
title: Visual Studio 项目模板 |Microsoft Docs
description: 描述.btproj、 bpel 格式，以及所使用的 BizTalk Server.btaproj Visual Studio 模板
ms.custom: ''
ms.date: 11/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2b3d494-db80-4314-afcd-d08d5a26e211
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d35eb4f12bdb7a66da28d94c8fabd33b073127
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018365"
---
# <a name="biztalk-server-project-templates"></a>BizTalk Server 项目模板

## <a name="overview"></a>概述
当你安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，安装将添加到 BizTalk 项目文件夹**新建项目**对话框。 BizTalk 项目文件夹包含用于创建一个空的 BizTalk Server 项目、 BizTalk Server BPEL 导入项目和 BizTalk Server 应用程序项目模板。

## <a name="available-templates"></a>可用模板
下表描述这些项目模板。  


|                     使用此选项                      |                                                                                                                                                                   执行的操作                                                                                                                                                                   |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **空的 BizTalk Server 项目**          |                                                                                                                                                  创建新的空 BizTalk Server 项目。                                                                                                                                                   |
|      **BizTalk Server BPEL 导入项目**       |                                                                                      将业务流程执行语言 (BPEL)、 Web 服务描述语言 (WSDL) 或 XML 架构定义语言 (XSD) 文件导入到 BizTalk 项目。                                                                                       |
| **BizTalk Server 应用程序项目 (.btaproj)** | 从开始[!INCLUDE[bts2016](../includes/bts2016-md.md)] [Feature Pack 1](../core/configure-the-feature-pack.md)，或更高版本。 <br/><br/>用于自动部署和更新使用 Visual Studio Team Services (VSTS) 的应用程序。 项目包含`BizTalkServerInventory.json`VSTS 在部署过程中使用的文件。 |

## <a name="see-also"></a>请参阅  
 [处理 BizTalk 项目](../core/working-with-biztalk-projects.md)
