---
title: ImportSettings 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587f7e1f-9cf7-4e7b-90cd-11a266f474dc
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040e0d827fd8039433ed950119e6c7b2d0ee3a9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332164"
---
# <a name="importsettings-command"></a>ImportSettings 命令
导入 BizTalk 组、 主机或主机实例设置从源 XML 文件配置数据库。 设置映射以及映射 XML 文件。 这些设置可能已导出中所述[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)或[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
## <a name="usage"></a>用法  
 `ImportSettings –Source:value –Map: value [-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>Parameters  
  
|**参数**|Required|ReplTest1|  
|-------------------|--------------|-----------|  
|**-Source**|是|导出的设置 XML 文件的路径和文件名称。|  
|**-Map**|是|映射 XML 文件的路径和文件名称。|  
|**-Server**|可选|承载 BizTalk 配置数据库的 SQL Server 计算机的名称。|  
|**-Database**|可选|BizTalk 配置数据库的名称。|  
  
## <a name="sample"></a>示例  
 `BTSTask ImportSettings /Source:”C:\My Folder>\ExportedSettings.xml” /Map:Mappings.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)