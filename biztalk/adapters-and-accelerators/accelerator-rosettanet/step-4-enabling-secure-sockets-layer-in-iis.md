---
title: "步骤 4： 启用安全套接字在 IIS 中的层 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Secure Socket Layers
- IIS
- double action tutorial, enabling SSL in IIS
- SSL
ms.assetid: 96109294-595a-46ac-974e-33123df79ed5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05bd6b06ddc54ec0d337dd7dddfff300a625f7df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a>步骤 4： 启用安全套接字在 IIS 中的层
安全套接字层 (SSL) 是一个协议，旨在增强客户端与服务器之间通信通道的安全性。 通过在 Microsoft® Internet 信息服务 (IIS) 7.5/7.0 中启用 SSL，Contoso 和 Fabrikam 组织在通信中对所有的数据传输使用身份验证和加密。 在此步骤中，您将学习如何在 IIS 7.5/7.0 中启用 SSL。  
  
> [!NOTE]
>  在 Contoso 和 Fabrikam 计算机上都必须执行此步骤。  
  
### <a name="to-prepare-a-new-server-certificate"></a>准备新服务器证书  
  
1.  单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，展开 **\<**  *computer_name*  **>**  (*本地计算机*)，展开**网站**，右键单击**Default Web Site**，然后单击**属性**。  
  
3.  在默认网站对话框中，在**目录安全性**选项卡上，单击**服务器证书**启动**IIS 证书向导**。  
  
4.  上**欢迎使用 Web 服务器证书向导**页上，单击**下一步**。  
  
5.  上**服务器证书**页上，选择**创建新证书**，然后单击**下一步**。  
  
6.  上**延迟或立即请求**页上，单击**下一步**。  
  
7.  上**名称和安全设置**页上，单击**下一步**，保留默认值。  
  
8.  上**组织信息**页上，在**组织**框中，键入**Contoso**如果已打开 Contoso 计算机或**Fabrikam**如果已打开Fabrikam 计算机，请在**组织单位**框中，键入**测试**，然后单击**下一步**。  
  
9. 上**站点的公用名称**页上，在**公用名**框中，键入你的计算机的名称，然后单击**下一步**。  
  
10. 上**的地理位置信息**页上，在**省/市/自治区**框中，键入你省自治区直辖市**城市/地点**框中，键入你城市/地点，，然后单击**下一步**。  
  
11. 上**证书请求文件名称**页上，在**文件名**框中，保留默认值**C:\certreq.txt**，然后单击**下一步**。  
  
12. 上**请求文件摘要**页上，单击**下一步**。  
  
13. 上**完成 Web 服务器证书向导**页上，单击**完成**关闭**IIS 证书向导**。  
  
### <a name="to-generate-a-new-server-certificate"></a>生成新服务器证书  
  
1.  在 Internet Explorer 中，找到并打开 http://\<*contoso_machine*> / CertSrv。  
  
    > [!NOTE]
    >  在步骤 1 中，打开 http://\<*contoso_machine*> / CertSrv Contoso 或 Fabrikam 计算机上的。  
  
2.  上**Microsoft 证书服务向导欢迎**页上，单击**请求证书。**  
  
3.  上**请求证书**页上，单击**高级的证书申请**。  
  
4.  上**高级证书申请**页上，单击**提交证书申请的步骤使用 base 64 编码 CMC 或 PKCS #10 文件，或使用 base 64 编码的 PKCS #7 文件提交续订申请**。  
  
5.  上**提交证书请求或续订请求**页上，单击**浏览要插入的文件**。  
  
    > [!NOTE]
    >  如果单击该链接时，你可以收到安全错误，在记事本或其他文本编辑器中打开文件 C:\certreq.txt、 复制文件的内容，并将该信息粘贴**保存请求**框中，并依次**提交**。 然后即可执行步骤 10。  
  
6.  单击**浏览**以打开**选择文件**对话框。  
  
7.  在**选择文件**对话框中，找到*\<驱动器 >*: \ 文件夹中，选择 certreq.txt 文件，然后单击**打开**。  
  
8.  上**提交证书请求或续订请求**页上，单击**读取**。  
  
9. 上**提交证书请求或续订请求**页上，单击**提交**来生成新证书。  
  
10. 上**颁发证书**页上，单击**下载证书**。  
  
11. 在**文件下载**对话框中，单击**保存**。  
  
12. 在**另存为**对话框中，保存到证书\<驱动器 >: \Certs\SSLCert.cer，，然后单击**保存**。  
  
13. 单击**关闭**关闭**下载已完成**对话框。  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a>为 IIS 准备新服务器证书  
  
1.  单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，单击 < 计算机名 > （本地计算机），双击**服务器证书**右窗格中。 选择**创建证书请求**从操作窗格。  
  
3.  可分辨名称属性对话框中键入的公用名中的计算机的名称： 文本框中，组织中： 框中，键入**Contoso**如果已打开 Contoso 计算机或**Fabrikam**如果已打开 Fabrikam计算机上的组织单位： 框中，键入测试，请在城市/地点框中，省/市/自治区框中键入你城市/地点，、 键入中的国家/地区下拉列表，选择你省自治区直辖市国家/地区，然后单击**下一步**.  
  
4.  在加密服务提供程序属性对话框中，单击**下一步**。  
  
5.  在文件名对话框中，在文本框中，指定 C:\certreq.txt 单击**完成**。  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a>为 IIS 生成新服务器证书  
  
1.  在 Internet Explorer 中，找到并打开 http://<contoso_machine>/CertSrv。  
  
    > [!NOTE]
    >  在步骤 1 中，打开 Contoso 或 Fabrikam 计算机上的 http://<contoso_machine>/CertSrv。  
  
2.  在 Microsoft 证书服务向导欢迎页上，单击**请求证书**。  
  
3.  在请求证书页中，单击**高级证书申请**。  
  
4.  在高级证书申请页上，单击**提交证书申请**通过使用 base 64 编码 CMC 或 PKCS #10 文件，或使用 base 64 编码的 PKCS #7 文件提交续订申请。  
  
5.  在记事本或其他文本编辑器中打开文件 C:\certreq.txt，复制文件的内容并将该信息粘贴**保存请求**框上提交证书请求，或续订请求的页上，并依次**提交**。  
  
6.  在证书颁发页上，单击**下载证书**。  
  
7.  在文件下载对话框中，单击**保存**。  
  
8.  在另存为对话框中，将保存到证书\<驱动器 >: \Certs\SSLCert.cer，，然后单击**保存**。  
  
### <a name="to-import-the-server-certificate-into-iis"></a>将服务器证书导入 IIS  
  
1.  单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，单击**（本地计算机）**，双击**服务器证书**右窗格中。 选择**完成证书请求**从操作窗格。  
  
3.  在指定的证书颁发机构响应对话框框中键入**\<驱动器 >: \Certs\SSLCert.cer**中**包含证书颁发机构的响应文件的名称**文本框。 中的友好名称文本框中键入**ContosoSSLCert**。  
  
### <a name="to-enable-ssl-bindings-for-iis"></a>为 IIS 启用 SSL 绑定  
  
1.  单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，展开**（本地计算机）**，展开**站点**，右键单击**Default Web Site**，然后单击**编辑绑定**。  
  
3.  在站点绑定对话框中单击**添加**。 在添加网站绑定对话框中选择**https**从类型下拉列表中，选择**ContosoSSLCert**从 SSL 证书下拉列表中，单击**确定**，单击**关闭**.  
  
### <a name="to-import-the-server-certificate-into-iis"></a>将服务器证书导入 IIS  
  
1.  单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，展开 **\<**  *computer_name*> (*本地计算机*)，展开**网站**，右键单击**Default Web Site**，然后单击**属性**。  
  
3.  在默认 Web 站点属性对话框中，在**目录安全性**选项卡上，单击**服务器证书**启动**IIS 证书向导**。  
  
4.  上**欢迎使用 Web 服务器证书向导**页上，单击**下一步**。  
  
5.  上**挂起的证书申请**页上，选择**处理挂起的请求和安装证书**，然后单击**下一步**。  
  
6.  上**处理挂起的请求**页上，在**路径和文件名**框中，键入**\<驱动器 >: \Certs\SSLCert.cer** （或浏览到该文件），然后单击**下一步**。  
  
7.  上**SSL 端口页**，单击**下一步**。  
  
8.  上**证书摘要**页上，单击**下一步**。  
  
9. 上**完成 Web 服务器证书向导**页上，单击**完成**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置 Contoso 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)