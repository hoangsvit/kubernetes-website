---
title: 为发行版本撰写功能特性文档
linktitle: 为发行版本撰写文档
content_type: concept
main_menu: true
weight: 20
card:
  name: contribute
  weight: 45
  title: 为发行版本撰写功能特性文档 
---
<!--
title: Documenting a feature for a release
linktitle: Documenting for a release
content_type: concept
main_menu: true
weight: 20
card:
  name: contribute
  weight: 45
  title: Documenting a feature for a release
-->

<!-- overview -->

<!--
Each major Kubernetes release introduces new features that require documentation.
New releases also bring updates to existing features and documentation
(such as upgrading a feature from alpha to beta).

Generally, the SIG responsible for a feature submits draft documentation of the
feature as a pull request to the appropriate development branch of the
`kubernetes/website` repository, and someone on the SIG Docs team provides
editorial feedback or edits the draft directly. This section covers the branching
conventions and process used during a release by both groups.
-->
Kubernetes 的每个主要版本发布都会包含一些需要文档说明的新功能。
新的发行版本也会更新已有的功能特性和文档（例如将某功能特性从 Alpha 升级为 Beta）。

通常，负责某功能特性的 SIG 要为功能特性的文档草拟文档，并针对 `kubernetes/website`
仓库的合适的开发分支发起拉取请求。
SIG Docs 团队会提供文字方面的反馈意见，或者直接编辑文档草稿。
本节讨论两个小组在分支方面和发行期间所遵从的流程方面的约定。

<!--
To learn about announcing features on the blog, read
[post-release communications](/docs/contribute/blog/release-comms/).
-->
要了解有关博客上发布新特性的信息，
请阅读[发布沟通](/zh-cn/docs/contribute/blog/release-comms/)。

<!-- body -->

<!--
## For documentation contributors

In general, documentation contributors don't write content from scratch for a release.
Instead, they work with the SIG creating a new feature to refine the draft documentation
and make it release ready.

After you've chosen a feature to document or assist, ask about it in the `#sig-docs`
Slack channel, in a weekly SIG Docs meeting, or directly on the PR filed by the
feature SIG. If you're given the go-ahead, you can edit into the PR using one of
the techniques described in
[Commit into another person's PR](/docs/contribute/review/for-approvers/#commit-into-another-person-s-pr).
-->
## 对于文档贡献者   {#for-documentation-contributors}

一般而言，文档贡献者不会为某个发行版本从头撰写文档。
相反，他们会与开发该功能特性的 SIG 团队一起，对文档草稿进行润色，
使之符合发布条件。

在你选定了某个功能特性，为其撰写文档（主笔或辅助），请在 `#sig-docs` Slack 频道、SIG Docs 的每周例会上，
或者在功能特性对应的 PR 上提出咨询。如果继续工作是没有问题的，
你可以使用[提交到他人的 PR](/zh-cn/docs/contribute/review/for-approvers/#commit-into-another-person-s-pr)
所述的某个技巧参与 PR 的编辑工作。

<!--
### Find out about upcoming features

To find out about upcoming features, attend the weekly SIG Release meeting (see
the [community](/community/) page for upcoming meetings)
and monitor the release-specific documentation
in the [kubernetes/sig-release](https://github.com/kubernetes/sig-release/)
repository. Each release has a sub-directory in the [/sig-release/tree/master/releases/](https://github.com/kubernetes/sig-release/tree/master/releases)
directory. The sub-directory contains a release schedule, a draft of the release
notes, and a document listing each person on the release team.
-->
### 了解即将发布的功能特性   {#find-out-about-upcoming-features}

要了解即将发布的功能特性，可以参加每周的 SIG Release 例会
（参考[社区](/zh-cn/community/)页面，了解即将召开的会议），
监视 [kubernetes/sig-release](https://github.com/kubernetes/sig-release/)
中与发行相关的文档。
每个发行版本在
[/sig-release/tree/master/releases/](https://github.com/kubernetes/sig-release/tree/master/releases)
下都有一个对应的子目录。
该子目录包含了发行版本的时间计划、发行公告的草稿以及列举发行团队名单的文档。

<!--
The release schedule contains links to all other documents, meetings,
meeting minutes, and milestones relating to the release. It also contains
information about the goals and timeline of the release, and any special
processes in place for this release. Near the bottom of the document, several
release-related terms are defined.

This document also contains a link to the **Feature tracking sheet**, which is
the official way to find out about all new features scheduled to go into the
release.
-->
发行时间计划文件中包含到所有其他文档、会议、会议记录及发行相关的里程碑的链接。
其中也包含关于发行版本的目标列表、时间线，以及当前发行版本中就绪的特殊流程的信息。
文档末尾附近定义了若干与该发行版本有关的术语。

此文档也包含到**功能特性跟踪清单**的链接。
这一清单是了解哪些功能特性计划进入某发行版本的正式途径。

<!--
The release team document lists who is responsible for each release role. If
it's not clear who to talk to about a specific feature or question you have,
either attend the release meeting to ask your question, or contact the release
lead so that they can redirect you.

The release notes draft is a good place to find out about
specific features, changes, deprecations, and more about the release. The
content is not finalized until late in the release cycle, so use caution.
-->
发行团队文档列举了哪些人扮演着各个发行版本的不同角色。
如果不清楚要联系谁来讨论特定的功能特性或者回答你的问题，
你可以参加发行团队的会议，提出你的问题，或者联系发行团队的牵头人，
这样他们就可以帮你找到正确的联系人。

发行说明草稿是用来发现与特定发行版本相关的功能特性、变更、废弃以及其他信息的好来源。
由于在发行周期的后段该文档的内容才会最终定稿，参考其中的信息时请谨慎。

<!--
### Feature tracking sheet

The feature tracking sheet [for a given Kubernetes release](https://github.com/kubernetes/sig-release/tree/master/releases)
lists each feature that is planned for a release.
Each line item includes the name of the feature, a link to the feature's main
GitHub issue, its stability level (Alpha, Beta, or Stable), the SIG and
individual responsible for implementing it, whether it
needs docs, a draft release note for the feature, and whether it has been
merged. Keep the following in mind:
-->
### 特性跟踪清单 {#feature-tracking-sheet}

针对[给定 Kubernetes 发行版本](https://github.com/kubernetes/sig-release/tree/master/releases)
特性跟踪清单中列举的是计划包含于该版本中的每个功能特性。
每一行中都包含特性的名称、特性对应的主要 GitHub Issue，其稳定性级别（Alpha、
Beta 或 Stable）、负责实现该特性的 SIG 和个人、是否该特性需要文档、
该特性的发行说明草稿以及该特性是否已经被合并等等。阅读此清单时请注意：

<!--
- Beta and Stable features are generally a higher documentation priority than
  Alpha features.
- It's hard to test (and therefore to document) a feature that hasn't been merged,
  or is at least considered feature-complete in its PR.
- Determining whether a feature needs documentation is a manual process. Even if
  a feature is not marked as needing docs, you may need to document the feature.
-->
- Beta 和 Stable 功能特性通常比 Alpha 特性更为需要文档支持。
- 如果某功能特性尚未被合并，就很难测试或者为其撰写文档。
  对于对应的 PR 而言，也很难讲特性是否完全实现。
- 确定某个功能特性是否需要文档的过程是一个手动的过程。
  即使某个功能特性没有标记需要文档，你仍可能需要为其提供文档。

<!--
## For developers or other SIG members

This section is information for members of other Kubernetes SIGs documenting new features
for a release.

If you are a member of a SIG developing a new feature for Kubernetes, you need
to work with SIG Docs to be sure your feature is documented in time for the
release. Check the
[feature tracking spreadsheet](https://github.com/kubernetes/sig-release/tree/master/releases)
or check in the `#sig-release` Kubernetes Slack channel to verify scheduling details and
deadlines.
-->
## 针对开发人员或其他 SIG 成员   {#for-developers-or-other-sig-members}

本节中的信息是针对为发行版本中新功能特性撰写文档的来自其他 Kubernetes SIG 的成员。

如果你是某个 SIG 的成员，负责为 Kubernetes 开发某一项新的功能特性，你需要与
SIG Docs 一起工作，确保这一新功能在发行之前已经为之撰写文档。
请参考[特性跟踪清单](https://github.com/kubernetes/sig-release/tree/master/releases)或者
Kubernetes Slack 上的 `#sig-release` 频道，检查时间安排的细节以及截止日期。

<!--
### Open a placeholder PR

1. Open a **draft** pull request against the
   `dev-{{< skew nextMinorVersion >}}` branch in the `kubernetes/website` repository, with a small
   commit that you will amend later. To create a draft pull request, use the
   **Create Pull Request** drop-down and select **Create Draft Pull Request**,
   then click **Draft Pull Request**.
1. Edit the pull request description to include links to [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes)
   PR(s) and [kubernetes/enhancements](https://github.com/kubernetes/enhancements) issue(s).
1. Leave a comment on the related [kubernetes/enhancements](https://github.com/kubernetes/enhancements)
   issue with a link to the PR to notify the docs person managing this release that
   the feature docs are coming and should be tracked for the release.
-->
### 提交占位 PR {#open-a-placeholder-pr}

1. 在 `kubernetes/website` 仓库上针对 `dev-{{< skew nextMinorVersion >}}`
   分支提交一个**draft** PR，其中包含较少的、待以后慢慢补齐的提交内容。
   要创建一个草案（draft）状态的 PR，可以在 **Create Pull Request** 下拉菜单中选择
   **Create Draft Pull Request**，然后点击 **Draft Pull Request**。
1. 编辑拉取请求描述以包括指向 [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) PR
   和 [kubernetes/enhancements](https://github.com/kubernetes/enhancements) 问题的链接。  
1. 在对应的 [kubernetes/enhancements](https://github.com/kubernetes/enhancements)
   issue 上添加评论，附上新 PR 的链接以便管理此发行版本的人员能够得到通知，
   了解特性的文档正在被撰写，在新的发行版本中要跟踪其进展。

<!--
If your feature does not need any documentation changes, make sure the sig-release team knows this,
by mentioning it in the `#sig-release` Slack channel. If the feature does need
documentation but the PR is not created, the feature may be removed from the milestone.
-->
如果对应的功能特性不需要任何类型的文档变更，请通过在 `#sig-release` Slack
频道声明这一点以确保 sig-release 团队了解。
如果功能特性确实需要文档，而没有对应的 PR
提交，该功能特性可能会被从里程碑中移除。

<!--
### PR ready for review

When ready, populate your placeholder PR with feature documentation and change
the state of the PR from draft to **ready for review**. To mark a pull request
as ready for review, navigate to the merge box and click **Ready for review**.

Do your best to describe your feature and how to use it. If you need help
structuring your documentation, ask in the `#sig-docs` Slack channel.

When you complete your content, the documentation person assigned to your feature reviews it.
To ensure technical accuracy, the content may also require a technical review from corresponding SIG(s).
Use their suggestions to get the content to a release ready state.
-->
### PR 准备好评阅  {#pr-ready-for-review}

时机成熟时，你可以在你的占位 PR 中完成功能特性文档，并将 PR 的状态从草案状态更改为
**Ready for Review**。要将一个拉取请求标记为已准备好评阅，
转到页面的 merge 框，点击 **Ready for review**。

尽可能为功能特性提供详尽文档以及使用说明。如果你需要文档组织方面的帮助，
请在 `#sig-docs` Slack 频道中提问。

当你已经完成内容撰写，指派给你的功能特性的文档贡献者会去评阅文档。
为了确保技术准确性，内容可能还需要相应 SIG 的技术审核。
尽量利用他们所给出的建议，改进文档内容以达到发布就绪状态。

<!-- 
If your feature needs documentation and the first draft
content is not received, the feature may be removed from the milestone.
-->
如果你的特性需要文档，而你未提交初版文档，那此特性可能会被从里程碑中移除。

<!--
#### Feature gates {#ready-for-review-feature-gates}
-->
#### 特性门控   {#ready-for-review-feature-gates}

<!--
If your feature is an Alpha or Beta feature and is behind a feature gate,
you need a feature gate file for it inside
`content/en/docs/reference/command-line-tools-reference/feature-gates/`.
The name of the file should be the name of the feature gate with `.md` as the suffix.
You can look at other files already in the same directory for a hint about what yours
should look like. Usually a single paragraph is enough; for longer explanations,
add documentation elsewhere and link to that.
-->
如果你在处理的特性处于 Alpha 或 Beta 阶段并由某特性门控控制，
你需要在 `content/en/docs/reference/command-line-tools-reference/feature-gates/` 目录中为其创建一个特性门控文件。
文件名应为特性门控的名称，并以 `.md` 作为后缀。
你可以参照同一目录中已存在的其他文件，以了解你的文件应该是什么样子的。
通常一段话就够了；若要长篇阐述，请在其他地方添加文档，并为其添加链接。

<!--
Also, to ensure your feature gate appears in the
[Alpha/Beta Feature gates](/docs/reference/command-line-tools-reference/feature-gates/#feature-gates-for-alpha-or-beta-features)
table, include the following details in the
[front matter](https://gohugo.io/content-management/front-matter/)
of your Markdown description file:
-->
此外，为了确保你的特性门控出现在
[Alpha/Beta 特性门控](/zh-cn/docs/reference/command-line-tools-reference/feature-gates/#feature-gates-for-alpha-or-beta-features)表格中，
请在 Markdown 描述文件的 [Front Matter](https://gohugo.io/content-management/front-matter/) 中包含以下细节：

<!--
```yaml
stages:
  - stage: <alpha/beta/stable/deprecated>  # Specify the development stage of the feature gate
    defaultValue: <true or false>     # Set to true if enabled by default, false otherwise
    fromVersion: <Version>            # Version from which the feature gate is available
    toVersion: <Version>              # (Optional) The version until which the feature gate is available
```
-->
```yaml
stages:
  - stage: <alpha/beta/stable/deprecated>  # 指定特性门控的开发阶段
    defaultValue: <true or false>     # 如果默认启用，则设置为 true，否则为 false
    fromVersion: <Version>            # 特性门控可用的起始版本
    toVersion: <Version>              # （可选）特性门控可用的结束版本
```

<!--
With net new feature gates, a separate description of the feature gate is also required;
create a new Markdown file inside `content/en/docs/reference/command-line-tools-reference/feature-gates/`
(use other files as a template).
-->
对于全新的特性门控，还需要一个单独的特性门控描述；在
`content/en/docs/reference/command-line-tools-reference/feature-gates/`
目录中创建一个新的 Markdown 文件（把其他文件用作模板）。

<!--
When you change a feature gate from disabled-by-default to enabled-by-default,
you may also need to change other documentation (not just the list of
feature gates). Watch out for language such as ”The `exampleSetting` field
is a beta field and disabled by default. You can enable it by enabling the
`ProcessExampleThings` feature gate.”
-->
当你将特性门控从默认禁用更改为默认启用时，你可能还需要更改其他文档（不仅仅是特性门控列表）。
参照这样的话术 “`exampleSetting` 字段是一个 Beta 字段，默认禁用。
你可以通过启用 `ProcessExampleThings` 特性门控来启用此字段。”

<!--
If your feature is GA'ed or deprecated, include an additional `stage` entry within
the `stages` block in the description file.
Ensure that the Alpha and Beta stages remain intact. This step transitions the
feature gate from the
[Feature gates for Alpha/Beta](/docs/reference/command-line-tools-reference/feature-gates/#feature-gates-for-alpha-or-beta-features) table
to [Feature gates for graduated or deprecated features](/docs/reference/command-line-tools-reference/feature-gates/#feature-gates-for-graduated-or-deprecated-features)
table. For example:
-->
如果你的特性已经是 GA（正式发布）或已弃用的，请在描述文件的 `stages` 块中包含一个额外的 `stage` 条目。
确保 Alpha 和 Beta 阶段保持不变。这一步将特性门控从
[Alpha/Beta 特性门控](/zh-cn/docs/reference/command-line-tools-reference/feature-gates/#feature-gates-for-alpha-or-beta-features)
表格移到[已毕业或已弃用的特性门控](/zh-cn/docs/reference/command-line-tools-reference/feature-gates/#feature-gates-for-graduated-or-deprecated-features)表格。
例如：

<!--
{{< highlight yaml "linenos=false,hl_lines=10-17" >}}
stages:
  - stage: alpha 
    defaultValue: false
    fromVersion: "1.12"
    toVersion: "1.12"
  - stage: beta 
    defaultValue: true
    fromVersion: "1.13"
  # Added a `toVersion` to the previous stage.
    toVersion: "1.18"
  # Added 'stable' stage block to existing stages.
  - stage: stable
    defaultValue: true
    fromVersion: "1.19"
    toVersion: "1.27"
{{< / highlight >}}
-->
{{< highlight yaml "linenos=false,hl_lines=10-17" >}}
stages:
  - stage: alpha 
    defaultValue: false
    fromVersion: "1.12"
    toVersion: "1.12"
  - stage: beta 
    defaultValue: true
    fromVersion: "1.13"
  # 将 `toVersion` 添加到了前一个 stage
    toVersion: "1.18"    
  # 将 'stable' stage 代码块添加到了 stages 下 
  - stage: stable
    defaultValue: true
    fromVersion: "1.19"
    toVersion: "1.27"
{{< / highlight >}}

<!--
Eventually, Kubernetes will stop including the feature gate at all.
To signify the removal of a feature gate, include `removed: true` in
the front matter of the respective description file.
Making that change means that the feature gate information moves from the
[Feature gates for graduated or deprecated features](/docs/reference/command-line-tools-reference/feature-gates-removed/#feature-gates-that-are-removed)
section to a dedicated page titled
[Feature Gates (removed)](/docs/reference/command-line-tools-reference/feature-gates-removed/),
including its description.
-->
最终，Kubernetes 将完全停止包含此特性门控。为了表示某特性门控已被移除，
请在相应描述文件的 Front Matter 中包括 `removed: true`。
这种变更意味着特性门控及其描述从[已毕业或已弃用的特性门控](/zh-cn/docs/reference/command-line-tools-reference/feature-gates-removed/#feature-gates-that-are-removed)
部分移到名为[特性门控（已移除）](/zh-cn/docs/reference/command-line-tools-reference/feature-gates-removed/)的专用页面。

<!--
### All PRs reviewed and ready to merge

If your PR has not yet been merged into the `dev-{{< skew nextMinorVersion >}}`
branch by the release deadline, work with the docs person managing the release
to get it in by the deadline. If your feature needs documentation and the docs
are not ready, the feature may be removed from the milestone.
-->
### 所有 PR 均经过评审且合并就绪   {#all-prs-reviewd-and-ready-to-merge}

如果你的 PR 在发行截止日期之前尚未合并到 `dev-{{< skew nextMinorVersion >}}` 分支，
请与负责管理该发行版本的文档团队成员一起合作，在截止期限之前将其合并。
如果功能特性需要文档，而文档并未就绪，该特性可能会被从里程碑中去除。
