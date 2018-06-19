---
title: ImportParties 命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d43e2c-401c-4450-ad9b-2528086b99e4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15edad97134d3dbccc6f4b1af9395cb0bc01febd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257005"
---
# <a name="importparties-command"></a>ImportParties 命令
从导入的企业到企业方和协议中配置数据库的源 XML 绑定文件而不导入任何应用程序项目。 有关详细信息，请参阅**备注**本主题中。  

> [!IMPORTANT]
> 此命令是新开头 **[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，和任何更高版本。
  
> [!NOTE]
>  绑定中生成文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有指定的应用程序。 它们被导入到默认的应用程序中。  
  
## <a name="usage"></a>用法  
  **BTSTask ImportParties-源**:*值*[**-ExcludeEdiFallbackSettings**] [**-服务器**:*值*] [**-数据库**:*值*]
  
## <a name="parameters"></a>Parameters  
  
|参数|必需|值|  
|---|---|---|  
|**源代码** | 必需 | 要读取的 XML 绑定文件路径和文件名称。|
|**-ExcludeEdiFallbackSettings** | 可选 | 如果指定，将从绑定文件排除 edi 回退 （x12 和 edifact） 设置。  |
| **服务器** | 可选 | 承载 BizTalk 配置数据库的 SQL server 的名称。 |
| **数据库** | 可选 | BizTalk 配置数据库的名称。 |

## <a name="sample"></a>示例
  `BTSTask ImportParties  -Source:"C:\Temp\MyParties.Xml" -ExcludeEdiFallbackSettings`

## <a name="remarks"></a>注释
如果绑定文件还包含应用程序项目，然后将不导入它们。 将导入仅方和协议。