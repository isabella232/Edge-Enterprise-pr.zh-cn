---
title: 自托管 Microsoft Edge 扩展
ms.author: aspoddar
author: AndreaLBarr
manager: balajek
ms.date: 04/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 了解如何在企业中打包和自托管 Microsoft Edge 扩展。
ms.openlocfilehash: 403b6879b15c146f40fa2564da76eae59b2abe88
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11618042"
---
# <a name="self-host-microsoft-edge-extensions"></a><span data-ttu-id="f37cc-103">自托管 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="f37cc-103">Self-host Microsoft Edge extensions</span></span>

<span data-ttu-id="f37cc-104">本文提供有关将扩展打包到你自己的 Web 商店上托管的基本指南。</span><span class="sxs-lookup"><span data-stu-id="f37cc-104">This article provides basic guidance for packaging an extension to host on your own webstore.</span></span> <span data-ttu-id="f37cc-105">还包括有关如何将扩展部署到组织中的设备和用户的说明。</span><span class="sxs-lookup"><span data-stu-id="f37cc-105">It also includes instructions on how to deploy extensions to devices and users in your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f37cc-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="f37cc-106">Prerequisites</span></span>

<span data-ttu-id="f37cc-107">若要自托管自己的扩展，需要为扩展及其清单文件提供自己的 Web 托管服务。</span><span class="sxs-lookup"><span data-stu-id="f37cc-107">To self-host your own extensions, you will need to provide your own web hosting services for the extensions and their manifest files.</span></span>

 <span data-ttu-id="f37cc-108">以下步骤假定你已创建扩展，具有 XML 文件的一些经验，具有配置组策略的工作知识，并且知道如何使用 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="f37cc-108">The following steps assume that you’ve already created your extension, have some experience with XML files, have a working knowledge of configuring group policy, and know how to use the Windows registry.</span></span>

## <a name="publish-an-extension"></a><span data-ttu-id="f37cc-109">发布扩展</span><span class="sxs-lookup"><span data-stu-id="f37cc-109">Publish an extension</span></span>

<span data-ttu-id="f37cc-110">发布扩展之前，需要将其打包到 CRX (Chrome 扩展) 文件中。</span><span class="sxs-lookup"><span data-stu-id="f37cc-110">Before you publish an extension it needs to be packed into a CRX (Chrome extension) file.</span></span> <span data-ttu-id="f37cc-111">使用以下步骤作为打包扩展为 CRX 文件的指南。</span><span class="sxs-lookup"><span data-stu-id="f37cc-111">Use the following steps as a guide to packing an extension as a CRX file.</span></span>

1. <span data-ttu-id="f37cc-112">在 Microsoft Edge 地址栏中，转到"*edge://extensions*"，如果尚未启用，则打开"**开发工具**"模式。</span><span class="sxs-lookup"><span data-stu-id="f37cc-112">In the Microsoft Edge address bar, go to *edge://extensions* and turn on **Developer mode** if it’s not already enabled.</span></span>
2. <span data-ttu-id="f37cc-113">在 "**已安装的扩展**"下，单击 "**打包扩展**" 以创建 CRX 文件。</span><span class="sxs-lookup"><span data-stu-id="f37cc-113">Under **Installed extensions**, click **Pack Extension** to create the CRX file.</span></span>
3. <span data-ttu-id="f37cc-114">使用 "**包扩展**" 对话框查找具有扩展源的目录。</span><span class="sxs-lookup"><span data-stu-id="f37cc-114">Use the **Pack extension** dialog to find the directory that has the source for the extension.</span></span> <span data-ttu-id="f37cc-115">选择目录，然后单击"**打包扩展**"。</span><span class="sxs-lookup"><span data-stu-id="f37cc-115">Select the directory and then click **Pack extension**.</span></span>  <span data-ttu-id="f37cc-116">这将创建 CRX 文件以及 PEM 文件。</span><span class="sxs-lookup"><span data-stu-id="f37cc-116">This will create your CRX file, along with a PEM file.</span></span> <span data-ttu-id="f37cc-117">保存 PEM 文件，因为对扩展进行版本更新需要该文件。</span><span class="sxs-lookup"><span data-stu-id="f37cc-117">Save the PEM file because it’s needed for making version updates to the extension.</span></span> <span data-ttu-id="f37cc-118">下一个屏幕截图显示了用于定位扩展根目录的"**包扩展**"对话框。</span><span class="sxs-lookup"><span data-stu-id="f37cc-118">The next screenshot shows the **Pack extension** dialog for locating the root directory of the extension.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-pack-dialog.png" alt-text="用于查找扩展的源代码的"包扩展"对话框。":::

   > [!IMPORTANT]
   > <span data-ttu-id="f37cc-120">将 PEM 文件存储在安全的位置，因为它是扩展的密钥，并且在将来更新时需要用到。</span><span class="sxs-lookup"><span data-stu-id="f37cc-120">Store the PEM file in a safe location because it’s the key for the extension and it’s needed for future updates.</span></span>

4. <span data-ttu-id="f37cc-121">将 CRX 文件拖动到扩展窗口中，并确保它可以加载。</span><span class="sxs-lookup"><span data-stu-id="f37cc-121">Drag the CRX file into your extensions window and make sure that it loads.</span></span>
5. <span data-ttu-id="f37cc-122">测试扩展并记下 ID 字段 (这是 CRX ID) 和版本号。</span><span class="sxs-lookup"><span data-stu-id="f37cc-122">Test the extension and take note of the ID field (this is the CRX ID) and version number.</span></span> <span data-ttu-id="f37cc-123">稍后将需要此信息。</span><span class="sxs-lookup"><span data-stu-id="f37cc-123">You’ll need this information later.</span></span> <span data-ttu-id="f37cc-124">下一个屏幕截图显示了具有 CRX ID 的测试扩展。</span><span class="sxs-lookup"><span data-stu-id="f37cc-124">The next screenshot shows a test extension with its CRX ID.</span></span>

   :::image type="content" source="media/microsoft-edge-manage-extensions-webstore/manage-extensions-test-extension.png" alt-text="显示 CRX ID 的扩展示例":::

6. <span data-ttu-id="f37cc-126">将 CRX 文件上传到主机，并记下其下载位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="f37cc-126">Upload the the CRX file to the host and note the URL of the location it will be downloaded from.</span></span> <span data-ttu-id="f37cc-127">XML 清单文件需要此信息。</span><span class="sxs-lookup"><span data-stu-id="f37cc-127">This information is needed for the XML manifest file.</span></span>
7. <span data-ttu-id="f37cc-128">若要创建一个带有应用/扩展 ID、下载 URL 和版本的清单 XML 文件，请定义以下字段：</span><span class="sxs-lookup"><span data-stu-id="f37cc-128">To create a manifest XML file with the app/extension ID, download URL, and version, define the following fields:</span></span>  

   - <span data-ttu-id="f37cc-129">**appid** - 步骤 5 中的扩展 ID</span><span class="sxs-lookup"><span data-stu-id="f37cc-129">**appid** - The extension ID from step 5</span></span>
   - <span data-ttu-id="f37cc-130">**codebase** - 步骤 6 中 CRX 文件的下载位置</span><span class="sxs-lookup"><span data-stu-id="f37cc-130">**codebase** - The download location for the CRX file from step 6</span></span>
   - <span data-ttu-id="f37cc-131">**version** - 应用/扩展的版本，应该与扩展清单中指定的版本匹配。</span><span class="sxs-lookup"><span data-stu-id="f37cc-131">**version** - The version of the app/extension, which should match the version specified in the manifest of the extension.</span></span>

   <span data-ttu-id="f37cc-132">下一个代码段显示了 XML 清单文件的示例。</span><span class="sxs-lookup"><span data-stu-id="f37cc-132">The next code snippet shows an example of an XML manifest file.</span></span>

   ```xml
   <?xml version='1.0' encoding='UTF-8'?> 
   <gupdate xmlns='http://www.google.com/update2/response' protocol='2.0'> 
     <app appid='ekilpdeokbpjmminmhfcgkncmmohmfeb'> 
     <updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.0' /> 
     </app> 
   </gupdate> 
   ```

   <span data-ttu-id="f37cc-133">有关详细信息，请参阅 [在 Microsoft Edge 中自动更新扩展 - Microsoft Edge 开发](/microsoft-edge/extensions-chromium/enterprise/auto-update)。</span><span class="sxs-lookup"><span data-stu-id="f37cc-133">For more information, see [Auto-update extensions in Microsoft Edge - Microsoft Edge Development](/microsoft-edge/extensions-chromium/enterprise/auto-update).</span></span>

8. <span data-ttu-id="f37cc-134">将完成的 XML 文件上传到可下载的位置，并记录 URL。</span><span class="sxs-lookup"><span data-stu-id="f37cc-134">Upload the completed XML file to a location where it can be downloaded from, noting the URL.</span></span> <span data-ttu-id="f37cc-135">使用组策略安装扩展时将需要此 URL。</span><span class="sxs-lookup"><span data-stu-id="f37cc-135">This URL will be needed when you install the extension using a group policy.</span></span> <span data-ttu-id="f37cc-136">请参阅 [分发专用托管的扩展](#distribute-a-privately-hosted-extension)。</span><span class="sxs-lookup"><span data-stu-id="f37cc-136">See [Distribute a privately hosted extension](#distribute-a-privately-hosted-extension).</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f37cc-137">扩展的托管位置不需要身份验证。</span><span class="sxs-lookup"><span data-stu-id="f37cc-137">The hosting location for the extension doesn’t need authentication.</span></span> <span data-ttu-id="f37cc-138">无论在何处使用用户设备，都要能够访问它。</span><span class="sxs-lookup"><span data-stu-id="f37cc-138">It needs to be accessible by user devices wherever they might be used.</span></span>

## <a name="publish-updates-to-an-extension"></a><span data-ttu-id="f37cc-139">为扩展发布更新</span><span class="sxs-lookup"><span data-stu-id="f37cc-139">Publish updates to an extension</span></span>

<span data-ttu-id="f37cc-140">更改并测试更新的扩展后，你可以发布它。</span><span class="sxs-lookup"><span data-stu-id="f37cc-140">After you change and test the updated extension you can publish it.</span></span> <span data-ttu-id="f37cc-141">使用以下步骤作为发布更新的指南。</span><span class="sxs-lookup"><span data-stu-id="f37cc-141">Use the following steps as a guide for publishing an update.</span></span>

1. <span data-ttu-id="f37cc-142">使用下面的语法将扩展的 manifest.JSON 文件的版本号更改为更高的版本号：`"version":"versionString"`。</span><span class="sxs-lookup"><span data-stu-id="f37cc-142">Change the version number in your extension's manifest.JSON file to a higher number using the following syntax: `"version":"versionString"`.</span></span> <span data-ttu-id="f37cc-143">如果"版本"："1.0"，则可以更新为"版本"："1.1"或高于"1.0"的任何数字。</span><span class="sxs-lookup"><span data-stu-id="f37cc-143">If the "version":"1.0", then you can update to "version":"1.1" or any number higher than "1.0".</span></span>
2. <span data-ttu-id="f37cc-144">更新 XML 文件中 `<updatecheck>` 的"版本"，以匹配在上一步输入清单文件的版本数值。</span><span class="sxs-lookup"><span data-stu-id="f37cc-144">Update the "version" of `<updatecheck>` in the XML file to match the number that you put in the manifest file in the previous step.</span></span> <span data-ttu-id="f37cc-145">例如：</span><span class="sxs-lookup"><span data-stu-id="f37cc-145">For example:</span></span><br>`<updatecheck codebase='https://app.somecompany.com/extensionfolder/helloworld.crx' version='1.1' />`
3. <span data-ttu-id="f37cc-146">创建包含新更改的 CRX 文件。</span><span class="sxs-lookup"><span data-stu-id="f37cc-146">Create a CRX file that includes the new changes.</span></span> <span data-ttu-id="f37cc-147">转到 *edge://extensions* 并启用 **开发人员模式**。</span><span class="sxs-lookup"><span data-stu-id="f37cc-147">Go to *edge://extensions* and enable **Developer mode**.</span></span>
4. <span data-ttu-id="f37cc-148">单击 **打包扩展**，然后转到扩展源的目录。</span><span class="sxs-lookup"><span data-stu-id="f37cc-148">Click **Pack extension** and go to the directory for the extension source.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f37cc-149">使用在首次创建 CRX 文件时生成和保存的同一 PEM 文件。</span><span class="sxs-lookup"><span data-stu-id="f37cc-149">Use the same PEM file that was generated and saved the first time the CRX file was created.</span></span> <span data-ttu-id="f37cc-150">如果不使用相同的 PEM 文件，扩展的应用 ID 将会更改，并且更新将被视为新扩展。</span><span class="sxs-lookup"><span data-stu-id="f37cc-150">If you don't use the same PEM file the app ID of the extension will change and the update will be treated as a new extension.</span></span>

5. <span data-ttu-id="f37cc-151">将 CRX 文件拖放到扩展窗口中并验证它是否加载。</span><span class="sxs-lookup"><span data-stu-id="f37cc-151">Drag and drop the CRX file into the extensions window and verify that it loads.</span></span>
6. <span data-ttu-id="f37cc-152">测试更新的扩展。</span><span class="sxs-lookup"><span data-stu-id="f37cc-152">Test the updated extension.</span></span>
7. <span data-ttu-id="f37cc-153">将旧的 CRX 文件和 XML 文件替换为已更新扩展的新文件。</span><span class="sxs-lookup"><span data-stu-id="f37cc-153">Replace the old CRX file and XML file with the new files for the updated extension.</span></span>

<span data-ttu-id="f37cc-154">将在下一个策略同步周期中选择扩展的更改。</span><span class="sxs-lookup"><span data-stu-id="f37cc-154">The extension's changes will be picked up during the next policy sync cycle.</span></span> <span data-ttu-id="f37cc-155">有关更新扩展的详细信息，请参阅： [更新 URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) 和 [更新清单](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest)。</span><span class="sxs-lookup"><span data-stu-id="f37cc-155">For more information about updating extensions, see: [Update URL](/microsoft-edge/extensions-chromium/enterprise/auto-update#update-url) and [Update manifest](/microsoft-edge/extensions-chromium/enterprise/auto-update#updated-manifest).</span></span>

## <a name="distribute-a-privately-hosted-extension"></a><span data-ttu-id="f37cc-156">分发专用托管的扩展</span><span class="sxs-lookup"><span data-stu-id="f37cc-156">Distribute a privately hosted extension</span></span>

<span data-ttu-id="f37cc-157">你可以共享 CRX 文件的托管位置的链接，用户一旦在浏览器中输入 URL，就会下载并安装扩展。</span><span class="sxs-lookup"><span data-stu-id="f37cc-157">You can share the link of the location where the CRX file is hosted, and as soon as users enter the URL in their browser the extension will be downloaded and installed.</span></span> <span data-ttu-id="f37cc-158">用户可以从"edge://extensions"页面启用扩展。</span><span class="sxs-lookup"><span data-stu-id="f37cc-158">Users can enable the extension from the edge://extensions page.</span></span> <span data-ttu-id="f37cc-159">若要允许用户安装自托管扩展，你需要将扩展 CRX ID 添加到 [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) 策略。</span><span class="sxs-lookup"><span data-stu-id="f37cc-159">To allow users to install self-hosted extensions, you need to add the extension CRX IDs to the [ExtensionInstallAllowList](/deployedge/microsoft-edge-policies#extensioninstallallowlist) policy.</span></span>

<span data-ttu-id="f37cc-160">或者，可以使用组策略 [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) 在用户的设备上强制安装扩展。</span><span class="sxs-lookup"><span data-stu-id="f37cc-160">Alternatively, you can use group policy [ExtensionInstallForceList](/deployedge/microsoft-edge-manage-extensions-policies#force-install-an-extension) to Force-install an extension on your users’ devices.</span></span>

<span data-ttu-id="f37cc-161">可以将这些策略应用于所选用户和/或设备。</span><span class="sxs-lookup"><span data-stu-id="f37cc-161">You can apply these policies to your selected users, devices, or both.</span></span> <span data-ttu-id="f37cc-162">请记住，策略更新不是即时更新，并且策略设置需要一段时间才能生效。</span><span class="sxs-lookup"><span data-stu-id="f37cc-162">Remember though that policy updates are not instantaneous, and it will take time for the policy settings to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="f37cc-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f37cc-163">See also</span></span>

- [<span data-ttu-id="f37cc-164">在企业中管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="f37cc-164">Manage Microsoft Edge extensions in the enterprise</span></span>](microsoft-edge-manage-extensions.md)
- [<span data-ttu-id="f37cc-165">使用组策略管理 Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="f37cc-165">Use group policies to manage Microsoft Edge extensions</span></span>](microsoft-edge-manage-extensions-policies.md)
- [<span data-ttu-id="f37cc-166">ExtensionSettings 策略的详细指南</span><span class="sxs-lookup"><span data-stu-id="f37cc-166">Detailed guide to the ExtensionSettings policy</span></span>](microsoft-edge-manage-extensions-ref-guide.md)
- [<span data-ttu-id="f37cc-167">Microsoft Edge 扩展的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f37cc-167">FAQ for Microsoft Edge Extensions</span></span>](microsoft-edge-manage-extensions-faq.md)
- [<span data-ttu-id="f37cc-168">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="f37cc-168">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
