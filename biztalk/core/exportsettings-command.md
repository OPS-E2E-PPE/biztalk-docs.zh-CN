---
title: "ExportSettings 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c39ef6903affbd2a1446bbde18a56e1a7778c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exportsettings-command"></a>ExportSettings 命令
使用 ExportSettings 命令可以将 BizTalk Server 配置数据库中的 BizTalk Server 设置导出到 XML 文件中。 你可以然后导入这些设置另一个环境中所述[如何导入 BizTalk 设置使用设置仪表板](../core/how-to-import-biztalk-settings-using-settings-dashboard.md)或[如何导入 BizTalk 设置使用 BTSTask](../core/how-to-import-biztalk-settings-using-btstask.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
## <a name="usage"></a>用法  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>Parameters  
  
|**参数**|必需|值|  
|-------------------|--------------|-----------|  
|**-目标**|是|要写入的 XML 文件的路径和文件名。|  
|**服务器**|可选|承载 BizTalk 配置数据库的 SQL Server 的名称。|  
|**数据库**|可选|BizTalk 配置数据库的名称。|  
  
## <a name="sample"></a>示例  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>注释  
 参数不区分大小写。 指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。  
  
## <a name="see-also"></a>另请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)