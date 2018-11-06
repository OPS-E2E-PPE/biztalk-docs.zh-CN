---
title: 附录 c： 可再发行的 CAB 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2049d61-e169-4b30-869a-33d5af097941
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66b5ca07676ba40a9ef1b5536b2b05d5ba2e321b
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753125"
---
# <a name="appendix-c-redistributable-cab-files"></a>附录 C：可再发行的 CAB 文件
BizTalk Server 安装程序使用这些 CAB 文件。

## <a name="biztalk-2016-cab-files"></a>BizTalk 2016 CAB 文件

|“报表”|下载链接|  
|--------------|-------------------|  
|EN|<ul><li>**X64**<br /><br /> <ul><li>Windows Server 2016: [http://go.microsoft.com/fwlink/p/?LinkId=746413](http://go.microsoft.com/fwlink/p/?LinkId=746413)</li><li>Windows Server 2012 R2: [http://go.microsoft.com/fwlink/p/?LinkId=746412](http://go.microsoft.com/fwlink/p/?LinkId=746412)</li><li>Windows 10: [http://go.microsoft.com/fwlink/p/?LinkId=746408](http://go.microsoft.com/fwlink/p/?LinkId=746408)</li><li>Windows 8.1： [http://go.microsoft.com/fwlink/p/?LinkId=746411](http://go.microsoft.com/fwlink/p/?LinkId=746411)</li></ul></li><li>**X32**<br /><br /><ul><li>Windows 10: [http://go.microsoft.com/fwlink/p/?LinkId=746409](http://go.microsoft.com/fwlink/p/?LinkId=746409)</li><li>Windows 8.1： [http://go.microsoft.com/fwlink/p/?LinkId=746410](http://go.microsoft.com/fwlink/p/?LinkId=746410)</li></ul></li></ul>|  

> [!NOTE] 
> Windows 10 和 Windows Server 2016 与 Windows 8.1 和 Windows Server 2012 R2 使用相同的 CAB 文件。 因此，它们具有相同的文件名称。

## <a name="biztalk-2013-r2-and-2013-cab-files"></a>BizTalk 2013 R2 和 2013 CAB 文件  

|“报表”|下载链接|  
|--------------|-------------------|  
|EN|<ul><li>**X64**<br /><br /> <ul><li>Windows Server 2012: [http://go.microsoft.com/fwlink/p/?LinkId=269616](http://go.microsoft.com/fwlink/p/?LinkId=269616)</li><li>Windows Server 2008: [http://go.microsoft.com/fwlink/p/?LinkId=269613](http://go.microsoft.com/fwlink/p/?LinkId=269613)</li><li>Windows 8: [http://go.microsoft.com/fwlink/p/?LinkId=269615](http://go.microsoft.com/fwlink/p/?LinkId=269615)</li><li>Windows 7: [http://go.microsoft.com/fwlink/p/?LinkId=269614](http://go.microsoft.com/fwlink/p/?LinkId=269614)</li></ul></li><li>**X32**<br /><br /> <ul><li>Windows 8: [http://go.microsoft.com/fwlink/p/?LinkId=269612](http://go.microsoft.com/fwlink/p/?LinkId=269612)</li><li>Windows 7: [http://go.microsoft.com/fwlink/p/?LinkId=269611](http://go.microsoft.com/fwlink/p/?LinkId=269611)</li></ul></li></ul>|  

## <a name="important-info"></a>重要信息

- SQL XML 可能有其自己的软件要求（如 `.NET Framework 3.5` 和 `.NET Framework 2.0`），这不包括在 CAB 文件中。 如果 BizTalk Server 可访问 Internet，则可能会自动安装 SQL XML 软件要求。 如果 BizTalk Server 不可访问 Internet，请手动安装 SQL XML 软件要求。

- CAB 文件安装路径也会列在**Setup.xml**安装文件夹中的文件 ([!INCLUDE[btsBizTalkServerPathx64_md](../includes/btsbiztalkserverpathx64-md.md)]\<版本\>)。

- 运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序时，应在你的计算机上安装一些 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所需的软件。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装程序允许你选择是从 Web 下载必备软件，还是从 CAB 文件中提取这些必备软件。 如果你选择 CAB 文件，应在运行安装程序之前下载 CAB 文件。  

- 你不能使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 早期版本中的 CAB 文件。 你必须从该表提供的链接中下载 CAB 文件。  

- 您无法通过 Telnet 会话下载 CAB 文件。  
