---
title: "独立 MSBUILD |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21aa3693-3788-4874-b506-6f4584fb4fd5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcee1d06bf57eb2ea98c214501c2499f0ce83d95
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="standalone-msbuild"></a>独立 MSBUILD
**项目生成**组件的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用于构建 BizTalk Server solutions 无[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 若要安装**项目生成**组件在服务器上，选择**项目生成组件**选项**其他软件类别**在安装过程。 应取消选中**开发人员工具和 SDK**如要安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有的计算机上[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
 有关 MSBUILD 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)。  
  
## <a name="to-build-a-biztalk-project"></a>若要生成 BizTalk 项目  
  
1.  单击 **“开始”**，再单击 **“运行”**。  
  
2.  类型**cmd**，然后按 ENTER。  
  
3.  切换到项目目录，然后运行 MSBUILD 命令以生成 BizTalk 解决方案。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!TIP]
    >  你可能需要设置 PATH 环境变量，以指向的文件夹中的 msbuild.exe 驻留 (\<*windows 安装目录*\>\Microsoft.NET\Framework\v4)。