---
title: ExportSettings 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa34dab1-c854-473e-a693-43ba45624e16
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a521ec09017e1ea529dbeb097ce119edee69f7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388210"
---
# <a name="exportsettings-command"></a>ExportSettings 命令
使用 exportsettings 命令可将 BizTalk Server 设置导出从 BizTalk Server 配置数据库到 XML 文件。 你可以然后导入另一个环境中的这些设置中所述[如何导入 BizTalk 设置使用设置仪表板](../core/how-to-import-biztalk-settings-using-settings-dashboard.md)或[如何使用 BTSTask 导入 BizTalk 设置](../core/how-to-import-biztalk-settings-using-btstask.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
## <a name="usage"></a>用法  
 `ExportSettings –Destination:value[-Server:value] [-Database:value]`  
  
## <a name="parameters"></a>Parameters  
  
|**参数**|Required|ReplTest1|  
|-------------------|--------------|-----------|  
|**-Destination**|是|要写入的 XML 文件的路径和文件名称。|  
|**-Server**|可选|承载 BizTalk 配置数据库的 SQL Server 的名称。|  
|**-Database**|可选|BizTalk 配置数据库的名称。|  
  
## <a name="sample"></a>示例  
 `BTSTask ExportSettings /Destination:MyFile.xml /Server:MyServer /Database:MyMgmtDb`  
  
## <a name="remarks"></a>备注  
 参数不区分大小写。 不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。  
  
## <a name="see-also"></a>请参阅  
 [BTSTask 命令行参考](../core/btstask-command-line-reference.md)