# Full Changelog

This can be generated using the following Python code:

```python
import subprocess
from datetime import datetime

try:
    # Fetch the list of commits with commit hash, date, and message
    log_command = "git log --pretty=format:'%h|%ad|%s' --date=short"
    output = subprocess.check_output(log_command, shell=True, universal_newlines=True)

    # Split the output into individual commit lines
    commit_lines = output.strip().split('\n')

    # Create a dictionary to store commits grouped by year and month
    commits_by_year_month = {}

    # Process each commit line
    for commit_line in commit_lines:
        commit_parts = commit_line.split('|')
        commit_hash = commit_parts[0]
        commit_date = datetime.strptime(commit_parts[1], '%Y-%m-%d')
        commit_message = commit_parts[2]

        year = commit_date.year
        month = commit_date.strftime('%B')

        # Add the commit to the corresponding year and month
        if year not in commits_by_year_month:
            commits_by_year_month[year] = {}
        if month not in commits_by_year_month[year]:
            commits_by_year_month[year][month] = []

        formatted_commit = f"-   {commit_date.strftime('%Y-%m-%d')} ({commit_hash}): {commit_message}"
        commits_by_year_month[year][month].append(formatted_commit)

    # Generate the Markdown content
    markdown_content = ""
    for year, months in sorted(commits_by_year_month.items(), reverse=True):
        markdown_content += f"# {year}\n\n"
        for month, commits in sorted(months.items(), key=lambda x: datetime.strptime(x[0], '%B'), reverse=True):
            markdown_content += f"## {month}\n\n"
            for commit in commits:
                markdown_content += f"{commit}\n"
            markdown_content += "\n"

    # Save the Markdown content to a file
    with open("commit_history.md", "w") as file:
        file.write(markdown_content)

    print("Commit history has been saved to 'commit_history.md'.")

except subprocess.CalledProcessError as e:
    print(f"Error: {e}")
    print(f"Output: {e.output}")

except Exception as e:
    print(f"An error occurred: {e}")
```

## 2024

### March

* 2024-03-22 (df49d930): Merged PR 364: Deploy
* 2024-03-22 (19c161f4): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-22 (af912252): Merged PR 1259: updated
* 2024-03-22 (19cb77d1): updated
* 2024-03-22 (caadeac3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-22 (cb4a4740): Merged PR 1258: IRRF fixes
* 2024-03-22 (a8ab6904): IRRF fixes
* 2024-03-22 (db36e5d6): Merged PR 1256: fixed issue in blank page
* 2024-03-22 (f2b34f20): fixed issue in blank page
* 2024-03-22 (a162531a): Merged PR 1254: fixed issue in breadcrumbs
* 2024-03-22 (de6493dc): fixed issue in breadcrumbs
* 2024-03-22 (520d1c52): Merged PR 1253: Map popup link changes
* 2024-03-22 (61e653f6): Map popup link changes
* 2024-03-22 (488b263b): Merged PR 1251: tooltip for gender seal and dfp seal
* 2024-03-22 (9885764a): resolve lint issues
* 2024-03-22 (f59743e3): resolved merge conflict
* 2024-03-22 (c377d9a7): added tooltips for the gender seals and dfp seals
* 2024-03-22 (aa35f1b2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-22 (9aebb926): Merged PR 1246: Added CO file creation script
* 2024-03-22 (bb1c9688): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-22 (0cdb1127): Merged PR 1249: Replace "-" with "N/A"
* 2024-03-22 (3195166a): Replace "-" with "N/A"
* 2024-03-22 (6dd7c82f): Merged PR 1248: mapper changes
* 2024-03-22 (d76477f8): mapper changes
* 2024-03-22 (e1445bb8): Merged PR 1245: fixed issue inconsistent genTargetText and restricted navigation to bureau view on breadcrumb click
* 2024-03-22 (4c0c39e1): Added CO file creation script Corrected IRRF scores
* 2024-03-22 (da582ca9): restricted browsing to bureau filter on prod side
* 2024-03-22 (c245bc27): Merged PR 1243: Delivery color fixes
* 2024-03-22 (1d27ceb7): Color changes
* 2024-03-22 (3b7411dd): fixed issue in inconsistent genTargetText generation
* 2024-03-22 (ff126ab0): Delivery color fixes
* 2024-03-22 (3a0955b2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-22 (b06f23a6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app
* 2024-03-22 (7f0d2931): Merged PR 1241: perf 489 and routing fixes
* 2024-03-22 (4d7199e0): updated the color for breadcrumbs
* 2024-03-22 (d3f8896d): fixed merge conflict
* 2024-03-22 (6426a8ae): Merged PR 1240: Audit changes and filter integration in impact
* 2024-03-22 (895c4550): Tidy Up Individual IRRF CO Page
* 2024-03-22 (d958d893): removed unnecessary console.logs
* 2024-03-22 (65a89331): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-486-487
* 2024-03-21 (a44a9e0e): fixed issue
* 2024-03-21 (46fb36f4): audit changes for CO view
* 2024-03-21 (36007288): Audit changes and filter integration in impact
* 2024-03-21 (44632ab3): CHANGE URL
* 2024-03-21 (1aac9beb): Merge branch 'develop'
* 2024-03-21 (58316f1e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-21 (e2c6a89f): Merged PR 1239: Text fixes
* 2024-03-21 (b5d3579c): Text fixes
* 2024-03-21 (bc9a1749): Merged PR 1238: update irrf
* 2024-03-21 (b3225d9b): update irrf
* 2024-03-21 (cbbfa937): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-21 (91ba5ba1): Update azure-pipelines-server.yml for Azure Pipelines
* 2024-03-21 (abcf8d08): Merged PR 1237: changed version
* 2024-03-21 (85318b13): changed version
* 2024-03-21 (d495b3e4): update version
* 2024-03-21 (c3600141): Update azure-pipelines-server.yml for Azure Pipelines
* 2024-03-21 (b761704c): update version
* 2024-03-21 (ef7840af): change core tools to v4
* 2024-03-21 (4f23aade): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-21 (e1ffee96): Update azure-pipelines-server.yml for Azure Pipelines
* 2024-03-21 (604c603b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-489
* 2024-03-21 (71bfe57a): updated
* 2024-03-21 (7620aec3): added cards to main pages
* 2024-03-21 (4a3ebf29): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-21 (034d5465): Merged PR 1235: routing changes
* 2024-03-21 (f101b1ca): Merged PR 1234: CO perf chart changes
* 2024-03-21 (5b4d7b8c): IRRF changes
* 2024-03-21 (cb122aa8): removed unnecessary console.logs
* 2024-03-21 (00efe6f8): updated
* 2024-03-21 (1a332cac): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-486-487
* 2024-03-20 (133121f9): resolved merge conflict and fixed issue in icpe ratings
* 2024-03-20 (c56c0284): routing changes
* 2024-03-20 (83298a28): CO perf chart changes
* 2024-03-20 (bb9aa9bd): Merged PR 1233: Update IRRF
* 2024-03-20 (524294ea): Merged PR 1231: Map changes and added N/A instead of "-" and "XX"
* 2024-03-20 (68bff412): revert config changes
* 2024-03-20 (b1abda4f): resolve lint issues
* 2024-03-20 (94782381): corrected values
* 2024-03-20 (999a5a62): Merge branch 'develop' into testing-main
* 2024-03-20 (0503b68b): Merged PR 1232: change moonshot value
* 2024-03-20 (2b065367): change moonshot value
* 2024-03-20 (1666d8df): Map changes and added N/A instead of "-" and "XX"
* 2024-03-20 (cfad65b8): values changed
* 2024-03-20 (3589e45f): change moonshot values
* 2024-03-20 (fc614399): Changed namin
* 2024-03-20 (e09bc2ec): Merge branch 'irrf-update' into testing-main
* 2024-03-20 (0e3a3c19): change web url
* 2024-03-20 (29b9f098): Merge branch 'develop' into sesp-issue
* 2024-03-20 (6576f77a): Add irrf changes
* 2024-03-20 (71ace239): Merged PR 1229: UNDP blue changes and nav link changes
* 2024-03-20 (329fca46): UNDP blue changes and nav link changes
* 2024-03-20 (98c83367): Merged PR 1227: added compliance filter to QA Compliance table
* 2024-03-20 (791da5d2): Merged PR 1226: perf-471 perf-481 perf-484
* 2024-03-20 (314c8d84): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into routing-changes
* 2024-03-20 (8d9ce145): added compliance filter to QA Compliance table
* 2024-03-20 (0505fabc): perf-475
* 2024-03-19 (4d443269): Merged PR 353: Deploy
* 2024-03-19 (413bec37): resolved merge conflict
* 2024-03-19 (fc86b64f): perf-471 perf-481 perf-484
* 2024-03-19 (698163f3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-19 (84b97fcc): Merged PR 1225: Table text changes
* 2024-03-19 (09d5c5ad): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-19 (12406638): Table text changes
* 2024-03-19 (b5928736): Merged PR 1224: Color changes and card order changes
* 2024-03-19 (6a79c293): Color changes and card order changes
* 2024-03-19 (b60c8996): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-19 (a20fafbe): used location
* 2024-03-19 (0d8a6305): Merged PR 1223: remove selected bureaus from sesp and turnover
* 2024-03-19 (f7e024c2): remove bpps
* 2024-03-19 (504878ff): remove selected bureaus from sesp and turnover
* 2024-03-19 (b00ac087): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-19 (0f22e05c): Merged PR 1221: change contributions 2024 value
* 2024-03-19 (348382e2): change contributions 2024 value
* 2024-03-19 (9d092841): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-19 (7333aa8c): Merged PR 1220: Fixed stat cards text color
* 2024-03-19 (1fc955ca): Fixed stat cards text color
* 2024-03-19 (21a323b2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-19 (af60d2b7): Merged PR 1217: Text changes and color changes
* 2024-03-19 (8f2e22b3): Merged PR 1218: NS\_HQ having no numerical value
* 2024-03-19 (56ad1873): NS\_HQ having no numerical value
* 2024-03-19 (a85bf9c0): text changes and color changes
* 2024-03-19 (7e284c28): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-469
* 2024-03-19 (8702ede8): Merged PR 1215: added strings of indicator score cards and descriptions card to the sharepoint list and updated methodology link
* 2024-03-19 (374033c9): updated methodology link in homepage
* 2024-03-19 (57925a9e): updated
* 2024-03-19 (c6a44b96): Merged PR 1213: Add countrycode to null countries
* 2024-03-19 (fed591e5): Add countrycode to null countries
* 2024-03-19 (334af8c0): Merged PR 1212: resolve sesp issues
* 2024-03-19 (0df815f4): resolve sesp issues
* 2024-03-18 (1fbb526b): data source update sesp
* 2024-03-18 (7de50ef6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-18 (494e999f): Merged PR 1210: Country office list navigation
* 2024-03-18 (9790bece): Country office list navigation
* 2024-03-18 (5c17b335): Merged PR 1209: handle null values
* 2024-03-18 (cbce2aa9): handle null values
* 2024-03-18 (ace801f8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-468
* 2024-03-18 (96b8d6ef): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-18 (39ffdf93): Merged PR 1207: updated bureau filter for vacancy rate and turnover rate
* 2024-03-18 (cc9f007c): updated bureau filter for vacancy rate and turnover rate
* 2024-03-18 (2aca3c9f): updated
* 2024-03-18 (422d9df5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-18 (a430a1bc): Merged PR 1205: Table scrolling changes
* 2024-03-18 (d10bb9c3): Table Scroll changes
* 2024-03-18 (3b4fe426): Merged PR 1202: Add bureau data for efficiency
* 2024-03-18 (cc9da4c7): Merged PR 1203: highlight the corresponding bar when bureua filter is added
* 2024-03-18 (f92338ba): highlight the corresponding bar when bureua filter is added
* 2024-03-18 (3f072f23): Add bureau data for efficiency
* 2024-03-18 (683892d5): Merged PR 1200: changed the color of the bars in the turnover and vacancy rate charts in when...
* 2024-03-18 (54d9357a): changed the color of the bars in the turnover and vacancy rate charts in when bureauFilter is added
* 2024-03-18 (c8670859): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-461
* 2024-03-15 (d9ae9666): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-15 (4e443593): Merged PR 1198: SESP drill down page changes
* 2024-03-15 (676c53c1): SESP drill down page changes
* 2024-03-15 (bc8cc20d): Merged PR 1197: resolve sesp
* 2024-03-15 (326cb33c): resolve sesp
* 2024-03-15 (1b4c2562): Merged PR 1196: remove ratio
* 2024-03-15 (d2ff3070): remove ratio
* 2024-03-15 (01a29bc4): Merged PR 1195: resolve sesp issue
* 2024-03-15 (7cc99dfe): resolve sesp issue
* 2024-03-15 (c8b3b74d): Change configs
* 2024-03-15 (b0dacf8d): Merged PR 1193: refactor sesp
* 2024-03-15 (cc00a72c): refactor sesp
* 2024-03-15 (367d5cd9): Merged PR 1192: Changed the list name to badges
* 2024-03-15 (40ae822d): Merged PR 1191: Refactor irrf and sesp
* 2024-03-15 (4241e61c): changed the list to badges
* 2024-03-15 (d7da8c38): Refactor irrf and sesp
* 2024-03-15 (7f35faed): Project
* 2024-03-14 (18d05c5e): Merged PR 1190: Revert irrf changes
* 2024-03-14 (4e14f035): revert irrf changes
* 2024-03-14 (e3dafe6f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-14 (416ebf6b): Merged PR 1189: change sorting methodology
* 2024-03-14 (1c3e721b): change sorting methodology
* 2024-03-14 (7d3d5ade): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-14 (4ad103b4): Merged PR 1185: sharepoint list for gender and dfp seals done
* 2024-03-14 (b89c8e51): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-458
* 2024-03-14 (79d19be4): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-14 (ca911363): Merged PR 1186: SESP page changes
* 2024-03-14 (717f05b9): sharepoint list for gender and dfp seals done
* 2024-03-14 (8c362331): SESP page changes
* 2024-03-14 (663e7f43): Merged PR 1184: change filename in carbon
* 2024-03-14 (495ad01b): change filename in carbon
* 2024-03-14 (dab87600): Merged PR 342: Latest changes
* 2024-03-14 (ba2875df): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-14 (9a3019d3): Merged PR 1182: change column names of IRRF
* 2024-03-14 (c4bceab5): change column names of IRRF
* 2024-03-14 (dbd91063): Merged PR 1181: change column name of SESP
* 2024-03-14 (b19a9166): change column name of SESP
* 2024-03-14 (9941338b): Merged PR 1180: Rearrange datawarehouse files
* 2024-03-14 (125f048c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-14 (681dec80): Rearrange datawarehouse files
* 2024-03-14 (f0f9cd8c): Merged PR 1179: change sesp year column name
* 2024-03-14 (fdfb4f9d): change sesp year column name
* 2024-03-14 (b2b5e243): Merged PR 1177: sesp changes
* 2024-03-14 (0fa7bb3c): sesp changes
* 2024-03-13 (88d5eecf): Merged PR 1176: filtering sesp based on compliance
* 2024-03-13 (5277f8c4): filtering sesp based on compliance
* 2024-03-13 (f595c600): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-13 (a6651626): Merged PR 1175: Add alpha2 code
* 2024-03-13 (ecfd9862): Add alpha2 code
* 2024-03-13 (0d201332): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-13 (1d8d07fb): Merged PR 1174: Change downloadable filenames
* 2024-03-13 (8eee1e82): Change downloadable filenames
* 2024-03-13 (61e2dd64): Merged PR 1172: Data downloaded col name issue fixed
* 2024-03-13 (0e725d8d): Data downloaded col name issue fixed
* 2024-03-13 (4bca6625): Merged PR 1171: removed info icon from the indicator score card in drill down pages
* 2024-03-13 (ec7a377a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-464
* 2024-03-13 (0c7727d4): removed info icons in drill down pages report cards
* 2024-03-13 (015bccb4): Merged PR 1168: Changed cursor for global filter options
* 2024-03-13 (8c1543d6): Merged PR 1167: updated
* 2024-03-13 (75c041cd): Merged PR 1169: Change name
* 2024-03-13 (4842361f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-13 (d34a8b38): Change name
* 2024-03-13 (7a3ef5af): updated
* 2024-03-13 (2565e97f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-454
* 2024-03-13 (0c08a0af): updated
* 2024-03-13 (fc0886fb): Merged PR 1166: Change alpha2 to alpha3
* 2024-03-13 (f7555dd0): Change alpha2 to alpha3
* 2024-03-13 (7bdb3a26): Merged PR 1164: Dates updated GENDER\_PARITY
* 2024-03-13 (59497124): Dates updated GENDER\_PARITY
* 2024-03-13 (65f6022f): Merged PR 1163: Add regionalSESP indicator
* 2024-03-13 (1514d752): Add regionalSESP indicator
* 2024-03-13 (593f7a2e): Merged PR 1161: Home Page CO Key Indicator Score Card Text
* 2024-03-13 (71c21f4f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-13 (ff4f1aff): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-443
* 2024-03-13 (8dfe166b): added strings for key indicators in co home page
* 2024-03-13 (31ef4603): Merged PR 1159: added missing global search
* 2024-03-13 (2f11e8c6): added missing global search
* 2024-03-13 (968af936): Merged PR 1157: text changes
* 2024-03-13 (73a48d32): text changes
* 2024-03-13 (3dfcc667): Merged PR 1156: move using arrow up and down in cmd + k search bar done
* 2024-03-13 (4f93e938): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-13 (ec9fba32): added support to iterate the dropdown with arrow up and down keys
* 2024-03-12 (b1d6af6b): Merged PR 336: Deploy
* 2024-03-12 (0b089ee7): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-12 (4dcbcaaa): Merged PR 1155: irrf changes
* 2024-03-12 (972b433d): irrf changes
* 2024-03-12 (f5395912): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-12 (bcbf9c85): Merged PR 1154: Resolve CO page issues
* 2024-03-12 (913a4e24): Resolve CO page issues
* 2024-03-12 (0aab1435): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-12 (c54274e1): Merge branch 'develop'
* 2024-03-12 (4d311c04): Merged PR 1151: COUNTRY \_STAT CHANGES
* 2024-03-12 (7596eab7): server url changed
* 2024-03-12 (a0d7ff5f): COUNTRY\_STAT changes
* 2024-03-12 (de6daf3b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-12 (57800e15): Merged PR 1150: changed blob storage
* 2024-03-12 (f021cf8a): changed blob storage
* 2024-03-12 (42a94862): Merged PR 1149: Resolve carbon conflict issues
* 2024-03-12 (db61a1e1): resolve lint issues
* 2024-03-12 (1e79ca47): resolved carbon conflict issues
* 2024-03-12 (8b800b71): Merged PR 1148: Deploy refactoring changes
* 2024-03-12 (3b71f040): added esc and arrow up down navigation to recently visited section
* 2024-03-11 (320a9068): Merged PR 1144: updates
* 2024-03-11 (e72a47f7): updates
* 2024-03-11 (8c92d55f): Merged PR 1143: changes in filtering out unwanted values in bureau filter list
* 2024-03-11 (fbc5852f): changes in filtering out unwanted values in bureau filter list
* 2024-03-11 (0486b890): Merged PR 1142: Map component changes for manualCountryData
* 2024-03-11 (29a0262e): Map component changes for manualCountryData
* 2024-03-08 (99b5d199): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-08 (de44b2ab): Add country filter for vacanvy
* 2024-03-08 (6acc5616): Updated readme
* 2024-03-08 (2c5c93c0): Merged PR 1140: Bureau initial draft fixes
* 2024-03-08 (69f90389): Bureau initial draft fixes
* 2024-03-08 (be07c9f9): Merged PR 1138: added score card strings to sharepoint list
* 2024-03-08 (ca36f23f): added score card strings to sharepoint list
* 2024-03-07 (59a9f6c8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-07 (a8bd3536): Merged PR 1136: fixed issues
* 2024-03-07 (4ea3e7f0): fixed issues
* 2024-03-07 (0c15a16a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-07 (a9a25ce5): Merged PR 1134: fixed issues
* 2024-03-07 (4eeec5be): fixed issues
* 2024-03-07 (1253752f): Merged PR 1132: dropdown filter fixes
* 2024-03-07 (a7cacdc8): fixed issue in recently visited section spaces
* 2024-03-07 (ac2fb392): Merge branch 'develop' into testing
* 2024-03-07 (05bd8d46): refactor file indicators
* 2024-03-07 (ef938e36): fixed issues in global filter
* 2024-03-07 (812b5291): Merged PR 1129: Server url changed
* 2024-03-07 (c7c77e73): Server url changed
* 2024-03-07 (8d1e4b11): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-07 (aa3072c2): resolve merge conflict
* 2024-03-07 (bb03111b): Merge branch 'develop' into testing
* 2024-03-07 (65aba2a9): Resolve issues in accountability
* 2024-03-07 (733e6b11): Merged PR 1127: filter fixes
* 2024-03-07 (6d635685): filter fixes
* 2024-03-07 (ae8e84d7): Completed all
* 2024-03-07 (98138368): Merged PR 1126: Filter fixes
* 2024-03-07 (55686a4d): Filter fixes
* 2024-03-07 (4fd0db7a): Merged PR 1124: fixed ui issues
* 2024-03-07 (94036536): fixed ui issues
* 2024-03-07 (77249833): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-425
* 2024-03-07 (9b53b062): Merged PR 1122: updated
* 2024-03-07 (3249f762): changed to ctrl+k and cmd+k
* 2024-03-07 (ee4b9723): updated
* 2024-03-07 (9b4d0058): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-425
* 2024-03-07 (6e7e2776): Merged PR 1120: added library react-hotkeys-hook to listen to keypresses
* 2024-03-07 (3b10070e): added library react-hotkeys-hook to listen to keypresses
* 2024-03-07 (8ffaf162): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-28-minor-fixes
* 2024-03-06 (ce156c16): Latest audit fixes
* 2024-03-06 (78d11ba2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-425
* 2024-03-06 (bcdd7164): Merged PR 1118: updated logic for the hotkeys
* 2024-03-06 (c8c8947a): updated logic for the hotkeys
* 2024-03-06 (3013fa8a): Merged PR 1116: updated the styling of the global search and added the caching of values
* 2024-03-06 (d8d8719b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-425
* 2024-03-06 (0786c315): updated the styling of the global search and added the caching of values
* 2024-03-06 (3e814cb6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-06 (08808f12): Merged PR 1114: added link to methodology document
* 2024-03-06 (033c13ef): added link to methodology document
* 2024-03-06 (d899a6ca): merge dev into testinf
* 2024-03-06 (f83ca6e8): Merged PR 1112: responsive fixes
* 2024-03-06 (d605dcc2): responsive fixes
* 2024-03-06 (a372c4e5): fixed issue in filters of charts
* 2024-03-05 (36c9111d): Merged PR 1110: responsive fixes
* 2024-03-05 (a61d55d1): responsive fixes
* 2024-03-05 (d0f384b9): Fix compile issue
* 2024-03-05 (4d14793a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-05 (dccac06f): Merged PR 1109: Fixed the table max-width issue
* 2024-03-05 (2d80bf8d): Fixed the table max-width issue
* 2024-03-05 (eb2c20ce): Merged PR 1107: added a global search bar to search countries, bureaus, and indicators
* 2024-03-05 (68e1a2da): updated
* 2024-03-05 (1f468456): added the global search bar to search countries, bureaus, indicators
* 2024-03-05 (b588d683): Merged PR 1105: Responsive fixes
* 2024-03-05 (575e3dcc): Responsive fixes
* 2024-03-05 (4f013648): Merge branch 'develop' into testing
* 2024-03-05 (6a36fc82): Merged PR 1103: Map auto focusing issue fixed
* 2024-03-05 (68638f20): Map auto focusing issue fixed
* 2024-03-04 (f0184791): Merged PR 324: Deploy
* 2024-03-04 (6176dec0): Merged PR 1101: styles fixes
* 2024-03-04 (2abdd2b8): styles fixes
* 2024-03-04 (538e5ac6): minor fixes in PQA and Country office list page
* 2024-03-04 (96908b69): Merged PR 1100: updated
* 2024-03-04 (29b94f0d): updated
* 2024-03-04 (641af369): Merged PR 1099: updated
* 2024-03-04 (f02c9dce): updated
* 2024-03-04 (a93a3458): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-04 (9d7471bf): basic modal done
* 2024-03-04 (88e27c8c): Merged PR 1097: filter fixes
* 2024-03-04 (16ca9ac1): filter fixes
* 2024-03-04 (1697d0c9): Merge branch 'develop' into testing
* 2024-03-04 (cc44185d): Merged PR 1096: rsolve lint issues
* 2024-03-04 (0ed13c17): rsolve lint issues
* 2024-03-04 (d61f611b): Merged PR 1094: update file structure changes
* 2024-03-04 (03071c6f): Merged PR 1092: Home page changes
* 2024-03-04 (e825502b): Home page changes
* 2024-03-04 (eb2d23b4): update file structure changes
* 2024-03-04 (1c4c401e): Merged PR 1090: Refactor file uploading
* 2024-03-04 (29faf434): remove reading data from aggregations
* 2024-03-04 (5363da1d): remove uploading data to data folder
* 2024-03-04 (4dec2801): Merge branch 'develop' into perf-pqabl
* 2024-03-04 (1c8edfb7): push testing
* 2024-03-01 (f7bfe116): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-01 (c25f8c77): Merged PR 1088: sass issue fixed
* 2024-03-01 (87951970): sass issue fixed
* 2024-03-01 (9f4574ff): Merged PR 1087: drill down pages with score cards
* 2024-03-01 (504507d9): updated
* 2024-03-01 (167ce89e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-430
* 2024-03-01 (3f7a1275): Merged PR 1085: responsive fixes
* 2024-03-01 (9a622c11): responsive fixes
* 2024-03-01 (45b97fa2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-03-01 (b3e6ee2d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-430
* 2024-03-01 (6123ea88): added score cards to drill down pages in impact and accountability
* 2024-03-01 (ea1d33bf): Merged PR 1083: fixed responsive issues in COuntrYOfficeList
* 2024-03-01 (669229c5): fixed responsive issues in COuntrYOfficeList
* 2024-03-01 (54376191): Merged PR 1081: Bureau filter initial Draft changes
* 2024-03-01 (fa23b13a): header filter change
* 2024-03-01 (7718dd43): Heade bureau filter changes
* 2024-03-01 (10d4a38e): update files
* 2024-03-01 (5a736eae): header changes
* 2024-03-01 (e6887b1c): wefwef
* 2024-03-01 (4a47e30e): Merge branch 'perf-426' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-426
* 2024-03-01 (0f7d8435): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-426
* 2024-03-01 (0f9aff23): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-426
* 2024-03-01 (6f2f5d72): global filter changes
* 2024-03-01 (8dd0bbda): Merged PR 1080: resolve lint issues
* 2024-03-01 (199e6381): resolve lint issues
* 2024-03-01 (521a6f5b): Merged PR 1079: Resolve file downloaidng issue
* 2024-03-01 (a7f7b35a): added score cards for irrf page
* 2024-03-01 (883a315b): Resolve file downloaidng issue
* 2024-03-01 (d730b9eb): Merged PR 1077: change filename
* 2024-03-01 (d7afef32): Merged PR 1075: Search capability to filters
* 2024-03-01 (b92da955): change filename
* 2024-03-01 (e8c467fb): updated
* 2024-03-01 (ea4b019d): Merged PR 1076: resolve lint issues
* 2024-03-01 (650ae571): resolve lint issues
* 2024-03-01 (1d445ec2): Merged PR 1074: Order the country list
* 2024-03-01 (4c6e467d): Order the country list
* 2024-03-01 (8c4b9cf6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-425
* 2024-03-01 (be4af95e): added search ability to global filter

### February

* 2024-02-29 (49a206f3): Merged PR 319: Deploy
* 2024-02-29 (ca468679): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-29 (05fed13e): Merged PR 1073: change file column names
* 2024-02-29 (1152e1ef): change file column names
* 2024-02-29 (548c101b): Merged PR 1072: change file names
* 2024-02-29 (0b633052): change file names
* 2024-02-29 (3ea03de1): change the column name
* 2024-02-29 (27225776): Merged PR 1071: rename files
* 2024-02-29 (0caa7810): rename files
* 2024-02-29 (38afdc34): Merged PR 1070: resolved lint issues
* 2024-02-29 (c6f5f1d4): resolved lint issues
* 2024-02-29 (e8705cdd): Merged PR 1069: change filenames
* 2024-02-29 (29823ea1): change filenames
* 2024-02-29 (71f9e7de): added search to individual card/chart fitlers
* 2024-02-29 (ec174c37): Merged PR 1067: formatNumberToReadableMinMill change
* 2024-02-29 (f56657ca): formatNumberToReadableMinMill change
* 2024-02-29 (3892d1cd): Merged PR 1065: Countrt List updates
* 2024-02-29 (9ed7fabc): Countrt List updates
* 2024-02-29 (c98ca485): Merged PR 1063: Country office bureau order changes
* 2024-02-29 (c96527da): Country office bureau order changes
* 2024-02-29 (8e470f79): Merged PR 1062: PQA Country list
* 2024-02-29 (37239a95): PQA Country list
* 2024-02-29 (b65c6694): Merged PR 1059: updated
* 2024-02-29 (4cf8e1de): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-29 (5fd709b5): Merge branch 'develop' into minor-changes
* 2024-02-29 (761c5ad9): changed the max limit in icpe graph
* 2024-02-29 (c3cd0640): Merged PR 1061: Add file changes
* 2024-02-29 (095cbdd3): Add file changes
* 2024-02-29 (b8a81ee0): Merged PR 1060: add path to zip folder
* 2024-02-29 (4348fe9f): add path to zip folder
* 2024-02-29 (bc7c0824): updated
* 2024-02-28 (cf25fe54): Merged PR 1056: dynamic text and remaining texts
* 2024-02-28 (dfbcf388): Merged PR 1057: change processor path
* 2024-02-28 (03a1264a): change processor path
* 2024-02-28 (cc5f0b17): resolved remaining merge conflict
* 2024-02-28 (66f1c5d2): resolved merge conflict
* 2024-02-28 (2de797ee): added home page strings
* 2024-02-28 (29e481de): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-28 (8f14ec93): Merged PR 1026: \[Inprogress] Refactor Backend
* 2024-02-28 (0735b277): change config
* 2024-02-28 (4bb5bfd6): add countrylist file
* 2024-02-28 (06a1c1c1): change filters
* 2024-02-28 (14ac9d6d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-28 (5f44b892): Merged PR 1054: updated
* 2024-02-28 (6b4b4e9d): updated
* 2024-02-28 (9d5fd9f8): Merged PR 1053: added filters to audit completion chart
* 2024-02-28 (206f66ec): added filters to audit completion chart
* 2024-02-28 (0ac0d833): accountability page done
* 2024-02-28 (3b3690b3): Add country list endpoint
* 2024-02-27 (bb06839f): change cpd name
* 2024-02-27 (f5316725): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-27 (9bb7a62d): Merged PR 1052: updated
* 2024-02-27 (2a79c141): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into minor-changes
* 2024-02-27 (43426a01): updated
* 2024-02-27 (c06b5bcd): Remove text
* 2024-02-27 (ab11f3ce): Merge branch 'develop' into v4
* 2024-02-27 (a7ee4cbd): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-418
* 2024-02-27 (ec94cf92): updated
* 2024-02-27 (54853dbe): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-27 (9c80f053): Merged PR 1050: CountryOfficeList import in Web file
* 2024-02-27 (fa311b3f): Merge branch 'develop' into v4
* 2024-02-27 (e1894bdf): CountryOfficeList import in Web file
* 2024-02-27 (7fe9b037): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-27 (4a6757b3): Merged PR 1049: Country list page added and impact page moonshot updates
* 2024-02-27 (1e6be04d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-27 (aff72aba): Country list page added and impact page moonshot updates
* 2024-02-27 (2a4c1176): Merged PR 1048: Add moonshot indicator
* 2024-02-27 (8d517e11): add moonshot indicator
* 2024-02-27 (67c35c5b): change icpe score
* 2024-02-27 (cb7bceef): Update nav scores for icpe and moonshot
* 2024-02-27 (119c7047): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-27 (30864b90): Merge branch 'develop' into v4
* 2024-02-27 (fb1bc835): Merged PR 1047: Update method to calculate icpe data
* 2024-02-27 (73a7868a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-27 (ac16944d): Merge branch 'icpe-file-downloading-issue' into v4
* 2024-02-27 (797fbae9): Update method to calculate icpe data
* 2024-02-27 (e474ddfd): Merge branch 'develop' into v4
* 2024-02-27 (4bbc086d): Merged PR 1046: resolved icpe file downloading issue
* 2024-02-27 (a6dfb93d): resolved icpe file downloading issue
* 2024-02-27 (92de5bb2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-418
* 2024-02-27 (91526130): updated
* 2024-02-27 (64ebfbf7): resolve lint issues
* 2024-02-27 (9058d241): Merged PR 1044: irrf table changes and icpe changes
* 2024-02-27 (56243943): fixed issues in impact icpe
* 2024-02-27 (8fd4a769): Merged PR 1042: border with changes
* 2024-02-27 (225a5b1a): border with changes
* 2024-02-27 (2abb6d9c): Merge branch 'develop' into v4
* 2024-02-27 (0f5815c6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into minor-changes
* 2024-02-27 (03a75813): updated labels in irrf tables
* 2024-02-27 (8c5da02b): ompleted cpd icpe
* 2024-02-27 (09b32eb1): Merged PR 1041: SESP & PQA changes
* 2024-02-27 (08d6aaaf): SESP & PQA changes
* 2024-02-27 (136bc6a6): Merge branch 'develop' into v4
* 2024-02-27 (18193f04): updated
* 2024-02-27 (63d31edf): Merged PR 1040: Get data from data cube for ICPE
* 2024-02-27 (bdf8d657): Completed icpe file changes
* 2024-02-27 (2ba3d7fb): Merged PR 1038: pipeline graph chart updated and reduced SGDs to 214..75B
* 2024-02-27 (95539778): reduced investments in the SDGs to $214.75
* 2024-02-27 (05271234): updated pipelinge graph
* 2024-02-26 (69b2672a): Get data for ICPE using datacube
* 2024-02-26 (e492be3f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-26 (98498a7e): Merged PR 1034: updated
* 2024-02-26 (7b77ccac): Merged PR 1035: QA fix
* 2024-02-26 (92359efb): QA fix
* 2024-02-26 (2ffc826a): updated
* 2024-02-26 (4f150292): impact page dynamic texts done
* 2024-02-26 (a0572502): Merged PR 1032: PQA & SESP changes
* 2024-02-26 (9418ade2): Mobile header issue fixed
* 2024-02-26 (3979ed32): SESP PQA changes
* 2024-02-26 (47b4c9a1): Merged PR 1031: PQA and SESP changes
* 2024-02-26 (8df0b3ee): Add reload functionality
* 2024-02-26 (8f4a4167): PQA and SESP changes
* 2024-02-26 (9230d781): Merged PR 1029: CO changes
* 2024-02-26 (b0eaae48): CO changes
* 2024-02-26 (adcb8bba): Merged PR 1027: CO view readable num fixes, and fixed 0 issue in CO page
* 2024-02-26 (2eb4599e): CO view readable num fixes, and fixed 0 issue in CO page
* 2024-02-26 (2008a0ea): people page common charts and dynamic texts done
* 2024-02-26 (8afa19b0): removed space
* 2024-02-26 (5ea022d7): resolve lint issues
* 2024-02-26 (2d51a02b): efficiency and values page common charts static texts and dynamic texts in values page
* 2024-02-26 (090e893e): resolve lint issues
* 2024-02-26 (067dbed2): Merge branch 'develop' into v4
* 2024-02-26 (77cc17dd): resolve lint issues
* 2024-02-26 (3eb34b92): resolve lint issues
* 2024-02-26 (b19a69d2): Complete values page
* 2024-02-23 (b4da45e0): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-23 (14b07774): Chage chart
* 2024-02-23 (8b2d84c1): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-23 (ff05dcfb): Merged PR 1023: home page static text
* 2024-02-23 (c2b44b5d): resolved merge conflict and added missing strings
* 2024-02-23 (d0eb62c8): added home page static text
* 2024-02-23 (bb9d2e14): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-23 (49d59fae): Change pipeline to bar chart
* 2024-02-23 (e25d629c): resolved merge conflict
* 2024-02-23 (58cba8f1): updated
* 2024-02-22 (c978af4f): completed except global and CO
* 2024-02-22 (dbbd6705): Impact page static text done
* 2024-02-22 (55096b79): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-22 (4d3f29a5): Merged PR 1022: Fixed loading issue for SESP & PQA
* 2024-02-22 (eab6cd3c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-22 (610f6c99): Fixed loading issue for SESP & PQA
* 2024-02-22 (55881944): Merged PR 1021: People page static text, context to store text and values page tooltip content mismatch fixed
* 2024-02-22 (fb7cc448): updated
* 2024-02-22 (4c93b3ac): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-22 (ff360f99): create context to store text and people page static text done
* 2024-02-22 (6be47353): Merged PR 1019: import fix
* 2024-02-22 (25301b2f): import fix
* 2024-02-22 (fee258ac): Merged PR 1017: CO view changes
* 2024-02-22 (ceb67055): Merged PR 1015: Remove agreement signed from the total pipeline
* 2024-02-22 (c9457324): CO view changes
* 2024-02-22 (70da6153): completed home
* 2024-02-22 (567a7bca): remove HOME\_KEY\_STAT
* 2024-02-22 (e28d0cac): completed efficiency
* 2024-02-22 (7923633a): Merge branch 'develop' into v4
* 2024-02-22 (cd90d675): Remove agreement signed from the total pipeline
* 2024-02-22 (5d0e90be): completed people
* 2024-02-22 (dc617639): Merged PR 1014: updated
* 2024-02-22 (203036e0): updated
* 2024-02-22 (a6f29e80): Merged PR 1013: perf-405 & perf-410 done
* 2024-02-22 (c458b741): perf-405 & perf-410 done
* 2024-02-22 (613150e7): added strings for people page some graphs
* 2024-02-22 (74d93612): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-21 (b17f8263): Change font path
* 2024-02-21 (22bf3b5a): Fix compile error
* 2024-02-21 (11c900fe): Change font weight
* 2024-02-21 (1e310f16): Update font locations
* 2024-02-21 (e74c62ec): Merged PR 1009: static text for values page
* 2024-02-21 (72e7d97e): updated
* 2024-02-21 (6c5b3dfe): Merged PR 1008: CO view new stats added
* 2024-02-21 (9fa347b4): CO view new stats added
* 2024-02-21 (35e17c52): getting static text for values page and refactored code related to getting static text in efficiency page
* 2024-02-21 (91462268): completed values
* 2024-02-21 (20c298c8): Merged PR 1006: static text for efficiency page done
* 2024-02-21 (bceb252e): static text for efficiency page done
* 2024-02-21 (d15bf1b2): Merged PR 1005: Handled special character issues in pqa project title
* 2024-02-21 (42471a9a): Merge branch 'develop' into v4
* 2024-02-21 (01765398): handled special character issues in pqa project title
* 2024-02-21 (3432f112): Merged PR 1004: Create files for institutional expenditure
* 2024-02-21 (7b4d8782): Create files for institutional expenditure
* 2024-02-21 (924a8ecb): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-21 (1a46fbd3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-414-be
* 2024-02-20 (5f7ae810): Merged PR 1003: Remove special characters
* 2024-02-21 (1257f0df): remove logs
* 2024-02-21 (6fdd0668): Remove special characters
* 2024-02-20 (2077a117): Merged PR 1001: updated column vals
* 2024-02-20 (3c82c834): updated column vals
* 2024-02-20 (bbfd87cc): removed unwanted imports
* 2024-02-20 (b194a2ec): Merged PR 999: updated
* 2024-02-20 (0235e456): updated
* 2024-02-20 (7e8897ad): Merged PR 997: getting text from sharepoint list for delivery, delivery cummulative, contributions done
* 2024-02-20 (6ed7bb80): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-418
* 2024-02-20 (ecddb4e1): efficiency page get text for delivery, delivery cummulative and contributions chart from sharepoint list
* 2024-02-20 (0837ad8d): Merged PR 996: Update sf unity methodology
* 2024-02-20 (2d9257a4): Update sf unity methodology
* 2024-02-20 (67703810): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-20 (f0573904): Remove accountability hardcode
* 2024-02-20 (60a0bca8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app
* 2024-02-20 (99b53daf): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-20 (1f82576c): Merged PR 995: Change sf unity methodology
* 2024-02-20 (f1b9c979): Change sf unity methodology
* 2024-02-20 (aee14892): change timestamp to int
* 2024-02-20 (b1ef5398): Merged PR 993: Bug on Contributions CO Home Page
* 2024-02-20 (3c669e45): Bug on Contributions CO Home Page
* 2024-02-20 (01dfab00): change audit
* 2024-02-20 (f9c3731c): Merged PR 992: sticky header reverted
* 2024-02-20 (eef5ba24): sticky header reverted
* 2024-02-20 (c0519ac5): Merged PR 990: updated the class to hide
* 2024-02-20 (1e85cba3): updated the class to hide
* 2024-02-19 (9179032e): Merge branch 'develop' into v4
* 2024-02-19 (12e3b488): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-19 (06d61770): update file names
* 2024-02-19 (738e8143): change file read and writes
* 2024-02-19 (7b894164): Merged PR 989: Change database
* 2024-02-19 (3ccb3c15): Change database
* 2024-02-19 (b02c8bfb): Merge branch 'develop' into v4
* 2024-02-19 (55969dc0): Update uploading functionality
* 2024-02-19 (7dc23656): add comun rounding methods
* 2024-02-19 (149e5486): Update files
* 2024-02-19 (cc7082a5): Merged PR 987: hide the sharepoint nav on desktop screens
* 2024-02-19 (284f96db): hide the sharepoint nav on desktop screens
* 2024-02-19 (ef92893b): Merge branch 'develop' into v4
* 2024-02-16 (5fd9b645): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-16 (09d379d1): resolve lint issues
* 2024-02-16 (e3150fa3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-16 (b422d173): Merged PR 986: Resolve pqa issue
* 2024-02-16 (1f5ece11): Resolve sesp issue
* 2024-02-16 (47c7fcb4): Merge branch 'main' of https://dev.azure.com/Performance-App/Performance%20App/\_git/Performance%20App
* 2024-02-16 (66efd0d3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app
* 2024-02-16 (3677c9e4): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-16 (6059a00b): Merged PR 984: fixed issue in efficiency page not redirecting
* 2024-02-16 (b1932232): fixed issue in efficiency page not redirecting
* 2024-02-16 (e94d42e4): Change file structure
* 2024-02-16 (fc661250): change statrecords
* 2024-02-16 (b33c5c1d): Merged PR 982: hide cpd naviagtion
* 2024-02-16 (54af13e3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-339
* 2024-02-16 (99d0ab4f): updated
* 2024-02-16 (02c59e1b): Merged PR 980: SESP & PQA changes
* 2024-02-16 (bd16d1b6): SESP & PQA changes
* 2024-02-16 (44b0e849): change blob storage file saving structure
* 2024-02-15 (9a94a22e): Update azure-pipelines-web.yml for Azure Pipelines
* 2024-02-15 (39b5c783): Update azure-pipelines-web.yml for Azure Pipelines
* 2024-02-15 (09dea78e): Update azure-pipelines-web.yml for Azure Pipelines
* 2024-02-15 (700445c6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-15 (d4929295): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app
* 2024-02-15 (30c3f571): Merged PR 978: added tables for QA completion projects and SESP completed projects
* 2024-02-15 (18e0f516): added tables for QA completion projects and SESP completed projects
* 2024-02-15 (3b32bb7c): Merge branch 'develop' into v4
* 2024-02-15 (d4c00de4): Merged PR 976: lint fixes
* 2024-02-15 (af90b5fc): lint fixes
* 2024-02-15 (1348be6a): Merged PR 975: lint fixes
* 2024-02-15 (b8b3861c): lint fixes
* 2024-02-15 (5b840b3f): Merged PR 974: lint issues fixed
* 2024-02-15 (4700e0c1): lint issues fixed
* 2024-02-15 (b5c137bd): Merged PR 972: Sticky header fixes and added the table data for SESP and PQA
* 2024-02-15 (762317bd): Merged PR 973: tab for cpd management only showing when country is selected in global filter
* 2024-02-15 (8e850bd5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-414-be
* 2024-02-15 (6b6cae10): tab for cpd management only showing when country is selected in global filter
* 2024-02-15 (b9daf142): Sticky header fixes and added the table data for SESP and PQA
* 2024-02-15 (e78b4f69): Merged PR 970: Change qa and sesp files
* 2024-02-15 (c26a41bf): Change files
* 2024-02-15 (baa5e328): resolve merge conflicts
* 2024-02-15 (d3ef5e68): Merge branch 'develop' into v4
* 2024-02-15 (0d875989): Merged PR 968: removed off-track and on-track from turnover and gender partity cards in co p...
* 2024-02-14 (fa47d7c1): updated table widths
* 2024-02-14 (eecc84a0): converted to mills contributions score
* 2024-02-14 (72b88b43): Merged PR 969: Resolve issue in esource mobilization
* 2024-02-14 (2953d51f): remov console logs
* 2024-02-14 (66e0b6ba): Resolve issue in resource mobilization
* 2024-02-14 (4d63be33): removed off-track and on-track from turnover and gender partity cards in co pages
* 2024-02-14 (1a744e69): Merge branch 'main' of https://dev.azure.com/Performance-App/Performance%20App/\_git/Performance%20App
* 2024-02-14 (9e8c1761): Merged PR 966: Add new colum to pqa and sesp
* 2024-02-14 (217b4c20): Add new colum to pqa and sesp
* 2024-02-14 (944d5c5c): Merged PR 963: hand icon for clickable components done
* 2024-02-14 (723501af): Merged PR 964: methodology fix for AUDIT\_LATEST\_RATING\_CO
* 2024-02-14 (db11d64b): methodology fix for AUDIT\_LATEST\_RATING\_CO
* 2024-02-14 (a350bd95): hand icon for clickable components done
* 2024-02-14 (01a1d926): Merged PR 962: added navigation to cpd managment
* 2024-02-14 (dd497eec): Merged PR 961: fixed mobile responsive issue in contribution score
* 2024-02-14 (d81fa92b): added navigation to cpd managment
* 2024-02-14 (ed871edc): fixed mobile responsive issue in contribution score
* 2024-02-14 (1b79f8df): Merged PR 959: Change country names
* 2024-02-14 (2fca79f8): Change country names
* 2024-02-14 (5ac64e97): Merged PR 958: changed audit to accountability
* 2024-02-14 (9f378008): changed audit to accountability
* 2024-02-14 (19e8787a): Merged PR 957: updated table style
* 2024-02-14 (8b6f6673): updated table style
* 2024-02-14 (cf238f5e): Merged PR 955: filter changes in IMPACT mapper
* 2024-02-13 (474ed440): Merge branch 'staging'
* 2024-02-13 (a588f318): Staging name change
* 2024-02-13 (54333e5a): IMPACT\_ALL\_IRF, IMPACT\_MOST\_STRUGGLING\_IND integration changes
* 2024-02-13 (d8f28007): filter changes in IMPACT mapper
* 2024-02-13 (6e1fe765): Merged PR 294: Deploy
* 2024-02-13 (9d886f45): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-13 (33d0237e): Merged PR 954: header sticky part z-index changed
* 2024-02-13 (abab1b0b): header sticky part z-index changed
* 2024-02-13 (ecf3b5a4): Merged PR 293: Deploy
* 2024-02-13 (03a9f0bc): Deleted azure-pipelines-test.yml
* 2024-02-13 (0ace26f0): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-13 (0a465a3c): Set up CI to update data files
* 2024-02-13 (a6a04302): Merged PR 952: updated
* 2024-02-13 (8e421f55): updated
* 2024-02-13 (50cfba51): Change to general names
* 2024-02-13 (c9c56b6b): Merged PR 950: updated the query
* 2024-02-13 (d1c76a14): updated the query
* 2024-02-13 (dddd6d58): Merged PR 949: Sticky header changes
* 2024-02-13 (d1f3ba3e): Sticky header changes
* 2024-02-13 (595c6ecc): Add structure to stage
* 2024-02-13 (893a93c8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-13 (93b586aa): rename proj file
* 2024-02-13 (305ffdb0): Merged PR 948: fixed alignment issue
* 2024-02-13 (1918f786): Merged PR 947: made the cards fit the page
* 2024-02-13 (338a53bc): fixed alignment issue
* 2024-02-13 (45684b0b): made the cards fit the page
* 2024-02-13 (c91871bc): adding new test folder
* 2024-02-13 (39fd93cf): Merged PR 944: PEOPLE\_TURNOVER indicator score fix in overview and AUDIT\_LATEST\_RATING\_CO me...
* 2024-02-13 (419bb746): Merged PR 945: added zero for empty bars people turnover rate
* 2024-02-13 (feefe10f): added zero for empty bars ub turnover rate
* 2024-02-13 (d53ed296): PEOPLE\_TURNOVER indicator score fix in overview and AUDIT\_LATEST\_RATING\_CO methodology fix
* 2024-02-13 (ca2d27ce): Merged PR 942: get data from static text list
* 2024-02-13 (7fad52aa): resolved merge conflict
* 2024-02-13 (0606a9ce): getting text from sharepoint list done
* 2024-02-12 (f4603df2): Merged PR 292: Deploy
* 2024-02-12 (70b6d964): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-12 (1a530ffa): Merged PR 940: Updated country\_lookup file
* 2024-02-12 (d2927827): updated country\_lookup file
* 2024-02-12 (b03948d3): Merged PR 291: Deploy
* 2024-02-12 (b11328a7): Fixed the statCard on track text color issue
* 2024-02-12 (169d0274): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-12 (ec66004c): change file names
* 2024-02-12 (b1561a6c): add validation
* 2024-02-12 (792a3ae6): Add error messages
* 2024-02-12 (39f13da6): Merge branch 'develop' into v4
* 2024-02-12 (f7df1a9f): Complete impact page
* 2024-02-12 (708bcf9d): Merged PR 938: changes for disabling multiplefilter option
* 2024-02-12 (6576179e): changes for disabling multiplefilter option
* 2024-02-12 (a7d04946): Merged PR 936: added sorting option for irrf output col
* 2024-02-12 (37a3aa0d): added sorting option for irrf output col
* 2024-02-09 (d6731fd1): Merged PR 290: Deploy
* 2024-02-09 (575784b7): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-09 (6c7cf69b): Merge branch 'develop' into v4
* 2024-02-09 (d8f3c83c): Merged PR 935: Remove console logs
* 2024-02-09 (c0b5bddd): Remove console logs
* 2024-02-09 (929e84d1): Merged PR 933: Order of IRRF Output changes
* 2024-02-09 (0d57532b): reorderIRRFOutputBasedOnOutputNum func changes
* 2024-02-09 (39d83b41): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-402-ui
* 2024-02-09 (90082da6): Order of IRRF Output changes
* 2024-02-09 (8ae2db5a): Merged PR 932: resolve lint issues
* 2024-02-09 (6970a64f): Add condition for qaData file
* 2024-02-09 (709158d0): resolve lint issues
* 2024-02-09 (f5d63198): Merged PR 931: update pqa & sesp
* 2024-02-09 (93292e99): update pqa & sesp
* 2024-02-09 (20c29a02): Merged PR 927: modified formatNumberToReadable function according to negative values
* 2024-02-09 (7561a022): Merged PR 929: changed title
* 2024-02-09 (d8953bae): changed title
* 2024-02-09 (f26b8be6): Merged PR 928: updated
* 2024-02-09 (53e47a70): updated
* 2024-02-09 (5c4e9384): modified formatNumberToReadable function according to negative values
* 2024-02-09 (d22ceb7f): Merged PR 926: country name changes
* 2024-02-09 (2beaeaac): country name changes
* 2024-02-09 (bd4cbd9f): Merged PR 924: updated
* 2024-02-09 (e7cf4a36): updated
* 2024-02-09 (bda521f0): Merged PR 923: Change SF unity
* 2024-02-08 (065eac8d): Merged PR 289: Deploy
* 2024-02-08 (28eadba9): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-08 (6ef2ced3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into static-text-from-list
* 2024-02-08 (51bb08cd): Change SF unity
* 2024-02-08 (91730032): Merged PR 922: updated
* 2024-02-08 (2a061d75): added dotted line for people turnover rate
* 2024-02-08 (7685d9a2): fixed issue in date formats
* 2024-02-08 (ef00858c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into minor-changes
* 2024-02-08 (ab9b78f0): updated
* 2024-02-08 (d13b6b16): intermediate
* 2024-02-08 (85dca272): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into static-text-from-list
* 2024-02-08 (2b01714e): updated
* 2024-02-08 (94a0c413): Merged PR 919: updated
* 2024-02-08 (69dcf587): Merged PR 920: guage component limit changes
* 2024-02-08 (d29aab52): guage component limit changes
* 2024-02-08 (b009e59d): Merged PR 918: Values section fix
* 2024-02-08 (15c867b1): Values section fix
* 2024-02-08 (be4306ef): updated
* 2024-02-08 (a563f65c): Merged PR 917: overall text change for efficiency, values pages and country office audit chart
* 2024-02-08 (a2e55a20): mapped definitiona and keys of country office audits
* 2024-02-08 (de3266af): added text changes for country office audits and values page
* 2024-02-08 (16c46ab4): Merged PR 915: Color methodology refactoring changes
* 2024-02-08 (8df5cc8e): Color methodology refactoring changes
* 2024-02-08 (01fd9783): updated files
* 2024-02-08 (79bc44c9): Merge branch 'files-updated' into v4
* 2024-02-08 (cc64d718): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into overall-text-changes
* 2024-02-08 (4e27171d): text-changes in efficiency page
* 2024-02-07 (e19f2c4d): Merged PR 288: Deploy
* 2024-02-07 (5c045c3d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-07 (5a4fc2e8): Merged PR 913: PQA fixes
* 2024-02-07 (bbdab854): PQA fixes
* 2024-02-07 (cf2b1035): Merged PR 287: Deploy
* 2024-02-07 (6e439e44): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-07 (3d114152): Merged PR 912: CO page score card fix
* 2024-02-07 (d2c0b3b5): CO page score card fix
* 2024-02-07 (a08cacb8): Merged PR 286: Deploy
* 2024-02-07 (81fd5f90): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-07 (9338cf80): Merged PR 910: PQA and sesp changes
* 2024-02-07 (02dd5c23): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-393-ui
* 2024-02-07 (9cce7244): PQA and sesp changes
* 2024-02-07 (f5dedffb): Merged PR 909: update qa and sesp
* 2024-02-07 (ae5b21db): Merged PR 908: overall text changes for CO pages
* 2024-02-07 (bb99cddc): update qa and sesp
* 2024-02-07 (8eb3308f): text changes
* 2024-02-07 (0883f70b): Merged PR 907: Update qa and sesp
* 2024-02-07 (08a581f8): Update qa and sesp
* 2024-02-07 (8c1ac334): Merged PR 906: stat rounded
* 2024-02-07 (98abfe96): Merged PR 285: Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git...
* 2024-02-07 (2a99e115): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-07 (0db7be17): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into staging
* 2024-02-07 (58421439): stat rounded
* 2024-02-07 (44da1ed3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-07 (9146e5d9): updated
* 2024-02-07 (04bf58e3): Merged PR 903: removed the top 10 deliveries chart and added to accumulated delivery page
* 2024-02-07 (01965c5b): Merged PR 904: ifd text change
* 2024-02-07 (77da9cd3): ifd text change
* 2024-02-07 (2c80f1d3): Merged PR 900: ifd integrations
* 2024-02-07 (c370f570): Merged PR 901: Add new file for bureau wise turnover
* 2024-02-07 (66cb3165): ifd integrations
* 2024-02-07 (11264379): removed the top 10 deliveries chart and added to accumulated delivery page
* 2024-02-07 (626bac29): Merged PR 898: ifdIndicator changes for AUDI\_NUM\_COUNTRIES
* 2024-02-07 (510aeb46): ifdIndicator changes for AUDI\_NUM\_COUNTRIES
* 2024-02-07 (cfb5f6d8): Add new file for bureau wise turnover
* 2024-02-07 (c548327c): Merged PR 897: dynamically change content on CO pages
* 2024-02-07 (848820ee): removed contribution text for cards and table in CO performance in CO pages
* 2024-02-07 (0e01490e): removed unnecessary console.log
* 2024-02-07 (287b2b76): updated how the QA completion data is taken
* 2024-02-07 (011d60c4): Merged PR 891: Add pqa and sesp data
* 2024-02-07 (f8e20bf7): Change nav stats
* 2024-02-07 (cf977a91): updated
* 2024-02-06 (fdb9dfd3): Merge branch 'staging' of https://dev.azure.com/Performance-App/Performance%20App/\_git/Performance%20App into staging
* 2024-02-06 (ba625812): Merge branch 'develop' into staging
* 2024-02-06 (9c6cf8d0): Merged PR 284: Revert 'Revert 'Deploy''
* 2024-02-06 (5407da19): Revert "Revert "Merged PR 281: Deploy""
* 2024-02-06 (c73b2663): Revert "Merged PR 282: Revert 'Deploy'
* 2024-02-06 (50d0251c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (885c8586): FIX LINT ISSUE
* 2024-02-06 (a1d4990c): Fix lint issue
* 2024-02-06 (f8d4f6c5): Stat text
* 2024-02-06 (96c5352b): pqa & sesp done
* 2024-02-06 (dcee05dc): Rename generateLabels
* 2024-02-06 (5403d1ec): Merged PR 282: Revert 'Deploy'
* 2024-02-06 (6c284d67): Revert "Merged PR 281: Deploy"
* 2024-02-06 (4544ad31): Merged PR 281: Deploy
* 2024-02-06 (3cba1114): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (ed1946cd): Fix home page
* 2024-02-06 (a89aa95a): change yearName
* 2024-02-06 (109bea93): change filenames
* 2024-02-06 (6bbff71a): Add pqa and sesp data
* 2024-02-06 (fbaff657): Merged PR 280: Deploy
* 2024-02-06 (257da03d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (66811c4a): Fix decimal issues
* 2024-02-06 (411c1f6b): Merged PR 889: Eng fixes
* 2024-02-06 (3f94e14d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-365-changes
* 2024-02-06 (29e8eaf9): Eng fixes
* 2024-02-06 (276b1211): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (0b241657): Fix 0s
* 2024-02-06 (b4636fac): Merged PR 888: Changed general value
* 2024-02-06 (af85f05d): Changed general value
* 2024-02-06 (3245ce7b): Merged PR 887: resolve lint issues
* 2024-02-06 (5b74279d): Remove normalization in data values
* 2024-02-06 (222b1da4): resolve lint issues
* 2024-02-06 (2161ade3): Merged PR 886: Add awaits to file updates
* 2024-02-06 (abe5af69): Add awaits to file updates
* 2024-02-06 (d86d5c42): Merged PR 884: Text changes and Methodology changes
* 2024-02-06 (a35c7050): Text changes and Methodology changes
* 2024-02-06 (0d88c6e7): Merged PR 883: Change the methodology to check country lookup file
* 2024-02-06 (d4354232): remove console logs
* 2024-02-06 (dd377efa): Change the methodology to check country lookup file
* 2024-02-06 (49d4203e): Merged PR 279: Deploy
* 2024-02-06 (a78312ed): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (3d163284): remove off track from year to date
* 2024-02-06 (ca3652fc): Merged PR 881: Congo fixes
* 2024-02-06 (97149e6b): Congo fixes
* 2024-02-06 (9a24c040): Fix rev
* 2024-02-05 (82910a2f): Merged PR 278: Deploy
* 2024-02-06 (51e79f7a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (bedb7ac7): Update global score
* 2024-02-05 (016489b9): Merged PR 277: Deploy
* 2024-02-06 (3bf01fe0): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (dbc3dab5): revert value
* 2024-02-05 (c5ffefe8): Merged PR 276: Deploy
* 2024-02-06 (1d709d9c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (fe394b99): Add text
* 2024-02-06 (ea5a9af8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-06 (25a64ca7): Text changes
* 2024-02-05 (2e9d1e79): Merged PR 879: Resolve delivery issue
* 2024-02-05 (472e10c7): Resolve delivery issue
* 2024-02-05 (f27a562c): Merged PR 878: Add institutinal resources
* 2024-02-05 (4242bd3d): Add institutinal resources
* 2024-02-05 (5508b7e7): Merged PR 877: Change indicator score
* 2024-02-05 (dd43cd39): Change indicator score
* 2024-02-05 (45f8e226): Merged PR 876: refactor efficiency page
* 2024-02-05 (d1a91f25): refactor efficiency page
* 2024-02-05 (d910ce0f): Merged PR 275: deploy
* 2024-02-05 (f934bcd3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (ee98a530): Update text
* 2024-02-05 (ca072a4a): Merged PR 274: Deploy
* 2024-02-05 (812ef28e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (c854a61c): Merged PR 874: cum avg fixes
* 2024-02-05 (aa0da1a2): cum avg fixes
* 2024-02-05 (5a1f562a): Merged PR 273: Deploy
* 2024-02-05 (8de4dbc6): Merged PR 272: Deploy
* 2024-02-05 (d4fae705): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (ac668191): change text
* 2024-02-05 (50592333): Merged PR 271: Deploy
* 2024-02-05 (63ec677c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (cd674655): Fix
* 2024-02-05 (1cf91ba3): Merged PR 872: added 2 countries
* 2024-02-05 (f59194a0): added 2 countries
* 2024-02-05 (15ccdbb2): Merged PR 270: Deploy
* 2024-02-05 (26381869): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (da7d7b50): Merged PR 871: cum avg fix
* 2024-02-05 (1c82b866): cum avg fix
* 2024-02-05 (463526f1): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (c895f89a): Merged PR 870: Change nav stats
* 2024-02-05 (73670bdb): Change nav stats
* 2024-02-05 (bd0e3eae): Merged PR 269: Deploying
* 2024-02-05 (73a57fe5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (1061e9a3): Merged PR 868: minor fixes
* 2024-02-05 (31263251): minor fixes
* 2024-02-05 (1881dc56): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (d4362a5b): fix spelling
* 2024-02-05 (7cbbf15c): Merged PR 867: Add two new countries
* 2024-02-05 (bdccc661): Add two new countries
* 2024-02-05 (bc0153f4): Merged PR 866: updated
* 2024-02-05 (29524b43): Text changes
* 2024-02-05 (cbe16deb): updated
* 2024-02-05 (131c46de): Merged PR 865: Add efficiency score
* 2024-02-05 (ce03ad36): Add efficiency score
* 2024-02-05 (fd7b88bf): Merged PR 864: Add year filter
* 2024-02-05 (8b5e5d36): Merged PR 268: Deploy
* 2024-02-05 (5ed08334): Add year filter
* 2024-02-05 (c547fce0): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (141f3934): Merged PR 862: updated
* 2024-02-05 (9056ef03): updated
* 2024-02-05 (ce5e1cd1): Merged PR 861: main stat card
* 2024-02-05 (92feda64): main stat card
* 2024-02-05 (17deae2e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (bfb3545b): Merged PR 859: key store stat meth changes
* 2024-02-05 (c0c38708): Merged PR 860: Add new score ratios
* 2024-02-05 (04465e02): Add new score ratios
* 2024-02-05 (8db11e7b): key store stat meth changes
* 2024-02-05 (78d786d2): Merged PR 267: Deploy
* 2024-02-05 (88b241fe): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (0674d353): Merged PR 857: Remove year filter for PQ SESP
* 2024-02-05 (89baf653): Merged PR 856: updated
* 2024-02-05 (51537dfc): Remove year filter for PQ SESP
* 2024-02-05 (8e7a31b3): updated
* 2024-02-05 (71d05e34): Merged PR 855: showing contribution percentage and fixed some issues in header score average
* 2024-02-05 (1069a278): updated
* 2024-02-05 (3883b38b): resolved merge conflict
* 2024-02-05 (959b2f70): updated
* 2024-02-05 (c962fc2b): updated
* 2024-02-05 (dad1af45): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (6d9e9067): Normalize turnover rate yearly value
* 2024-02-05 (7b06577c): Merged PR 266: Deploy
* 2024-02-05 (29587f80): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (683150b1): Merged PR 852: Cum avg global filter requirement changes
* 2024-02-05 (521205fe): Cum avg global filter requirement changes
* 2024-02-05 (7943abca): Merged PR 850: Add bureau filter
* 2024-02-05 (51a4c21b): Add bureau filter
* 2024-02-05 (2a475712): Merge branch 'develop' into v4
* 2024-02-05 (4e6f3e88): Merged PR 849: Change query of PQA
* 2024-02-05 (d975d01c): Add vacanacy file
* 2024-02-05 (c471f383): Change query of PQA
* 2024-02-05 (e2beea02): Merged PR 265: Deploy
* 2024-02-05 (5a38b4e3): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (99d1ba60): Merged PR 848: Add country wise vacancy indicator
* 2024-02-05 (83e7aa91): Add country wise vacancy indicator
* 2024-02-05 (b3a960ae): Merged PR 846: map blue opacity changes
* 2024-02-05 (c1b8093c): map blue opacity changes
* 2024-02-05 (7316b28b): Merged PR 844: Country Office Audit Color Methodology
* 2024-02-05 (91491741): Country Office Audit Color Methodology
* 2024-02-05 (a1063559): Merged PR 264: Deploy Text changes
* 2024-02-05 (93d7ad1d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-05 (40c32150): Merged PR 843: header changes
* 2024-02-05 (b9fda70e): fixed issue data update for headerscores
* 2024-02-05 (c5db3ab5): fixed issue in signature solution chart getting disapeared
* 2024-02-05 (ce942ce1): fixed issue in color inconsistencies in tab and tab select state
* 2024-02-05 (3ef6350a): removed header tab scores on global filter select
* 2024-02-05 (b6589a47): Merged PR 841: text-changes
* 2024-02-05 (036684a5): text-changes
* 2024-02-05 (7e21162f): Merged PR 839: CHanged the project map focused country color
* 2024-02-05 (6340b86e): CHanged the project map focused country color
* 2024-02-05 (fcbe3fc3): updated
* 2024-02-02 (e23ee76f): Merged PR 263: Deploy
* 2024-02-02 (1dbb6c50): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-02 (6ba85c13): Merged PR 837: gender parity fixes
* 2024-02-02 (1be4e5c0): gender parity fixes
* 2024-02-02 (d9f7b8e0): Merged PR 835: people section CO page changes
* 2024-02-02 (7e59d726): updated
* 2024-02-02 (a54a9f53): people section CO page changes
* 2024-02-02 (440ba45e): Merged PR 819: Dynamic text changes for Project Quality Assurance Compliance
* 2024-02-02 (3ed873de): Merged PR 831: cum avg stat changes
* 2024-02-02 (66b31c4b): Merged PR 833: Add turnover indicator score
* 2024-02-02 (90a3644c): Change country names in IRRF file
* 2024-02-02 (be547d6c): Merged PR 832: fixes for data inconsistencies in FE
* 2024-02-02 (9432aa26): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into static-text-from-list
* 2024-02-02 (5956419f): Merged PR 830: global turnover rate done
* 2024-02-02 (28d08a39): cum avg stat changes
* 2024-02-02 (a744a725): fixed issue in getting undefined for indicator score
* 2024-02-02 (c264d1ba): getting NAV\_STATS data on current path change
* 2024-02-02 (4e9c7a00): changed min height 125px -> 130px
* 2024-02-02 (3fb36532): updated
* 2024-02-02 (3c759afe): global turnover rate done
* 2024-02-02 (a33d2ebc): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-365-changes
* 2024-02-02 (3b0584ec): Merged PR 828: display scalelabel for Turnover CO
* 2024-02-02 (95b42fea): resolved merge conflict and added axis labels for CO turnover rate
* 2024-02-02 (882b4a89): Merged PR 829: moved turnover rate to top
* 2024-02-02 (e91edfc2): removed description text on engagement on globalFilter select
* 2024-02-02 (a0220165): moved turnover rate to top
* 2024-02-02 (ea1eb2c4): made the transparency index chart hide when global filter is selected
* 2024-02-02 (149a8980): display scalelabel for Turnover CO
* 2024-02-01 (8e27802f): Merged PR 262: Deploy
* 2024-02-01 (0b63fd2a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-02-01 (ab4b497f): Merged PR 826: turnover-rate-co
* 2024-02-01 (675e69af): added co turnover rate
* 2024-02-01 (cfed74ef): TurnOver stat score
* 2024-02-01 (e000cbb1): Merged PR 824: cum avg reverted
* 2024-02-01 (5ab6a05a): cum avg reverted
* 2024-02-01 (2dff1653): updated
* 2024-02-01 (039b30dc): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into turnover-rate-co
* 2024-02-01 (c85e81c8): Merged PR 823: updated
* 2024-02-01 (71980b49): updated
* 2024-02-01 (bf8f598b): basic setup
* 2024-02-01 (f11c5256): Vacancy Rate (Country Office) FE changes
* 2024-02-01 (b508c5c2): Vacancy Rate (Country Office) FE changes
* 2024-02-01 (0afa8025): Merged PR 821: Add turn Over
* 2024-02-01 (e83de192): Add turnOver
* 2024-02-01 (a4e89be8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into global-filter-changes-to-pages
* 2024-02-01 (6191f36c): Merged PR 820: global filter changes to engagement-rate
* 2024-02-01 (d50cdb28): left border added
* 2024-02-01 (62430a22): changes for people engagement co
* 2024-02-01 (be40770d): Dynamic text changes for Project Quality Assurance Compliance
* 2024-02-01 (eeac6293): Merged PR 818: Normalize values to 100
* 2024-02-01 (d6c27037): Normalize values to 100
* 2024-02-01 (96999843): Merged PR 816: fixed issues in irrf co pages
* 2024-02-01 (71c0004c): removeZeroDataValsIRRF\_KEY\_STAT
* 2024-02-01 (5320c523): removed zero vals in irrf key stat
* 2024-02-01 (3d471697): Merged PR 817: Reorder the positions list in response
* 2024-02-01 (15a68d69): reorder the list
* 2024-02-01 (6e76bb6d): remove console logs
* 2024-02-01 (8c144549): Resolve issue in top 5 projects
* 2024-02-01 (39356dbf): fixed issues in irrf co pages
* 2024-02-01 (a966b109): Merged PR 814: PEOPLE\_ENGAGEMENT integrations
* 2024-02-01 (ce03399d): Merged PR 813: AUDIT\_YEARLY\_COUNTRYVALUE integration changes
* 2024-02-01 (ba70cbf9): PEOPLE\_ENGAGEMENT integrations

### January

* 2024-01-31 (3a3c1a79): AUDIT\_YEARLY\_COUNTRYVALUE integration changes
* 2024-01-31 (87adcd9c): Merged PR 261: Deploy
* 2024-01-31 (d2eecaa9): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-31 (8960e67a): Merged PR 811: FE: IFD (Country Office) changes
* 2024-01-31 (5befa609): ifd chart CO changes
* 2024-01-31 (a4a5402c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-357-ui
* 2024-01-31 (59150b81): FE: IFD (Country Office) changes
* 2024-01-31 (c98997fc): Merged PR 810: changes
* 2024-01-31 (3282d4ee): global filter for gender parity
* 2024-01-31 (3174d4cd): extracted signature solutions to commoncharts
* 2024-01-31 (3e78c242): dynmaically change components, remove text when global filter is selected
* 2024-01-31 (aeab5853): Update azure-pipelines-files.yml for Azure Pipelines
* 2024-01-31 (bb8449fa): Merged PR 809: Add ifd co page indicator
* 2024-01-31 (9247ecf0): Add ifd co page indicator
* 2024-01-31 (5a1bb3af): Merged PR 807: SESP filter integrations
* 2024-01-31 (ea12db4f): Merged PR 808: Contributions (Country Office) and Delivery (Country Office) max value y axis...
* 2024-01-31 (f6adc3bb): Contributions (Country Office) and Delivery (Country Office) max value y axis changes
* 2024-01-31 (f727ad88): basic code
* 2024-01-31 (4238c859): SESP filter integrations
* 2024-01-31 (72520a8b): Merged PR 806: Change gender parity processor file
* 2024-01-31 (55345cbb): Change gender parity processor file
* 2024-01-30 (427e7dae): Merged PR 260: Deploy
* 2024-01-30 (07c765d5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-30 (40a1f247): Merged PR 803: fixed arrayToText func
* 2024-01-30 (bb043a09): Merged PR 804: resolve engagement issue
* 2024-01-30 (bc05d00f): resolve engagement issue
* 2024-01-30 (53b8f17e): fixed arrayToText func
* 2024-01-30 (14558ebc): Merged PR 259: Deploy
* 2024-01-30 (b53d8371): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-30 (f386c938): Merged PR 802: ArrayToText function fixes
* 2024-01-30 (4e061499): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into pqa-piechart-conv
* 2024-01-30 (f013863c): arrayToText function fixes
* 2024-01-30 (687be4e4): Merged PR 800: Add engagement stat
* 2024-01-30 (038bc55a): Add engagement stat
* 2024-01-30 (e3de66bf): Merged PR 258: Deploy
* 2024-01-30 (1759e704): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-30 (19609b08): Merged PR 799: PQA chart type changed and efficiency page text updates
* 2024-01-30 (98804b7a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into pqa-piechart-conv
* 2024-01-30 (c92652df): PQA chart type changed
* 2024-01-30 (140ed52d): Merged PR 798: Add bureau filter for SESP
* 2024-01-30 (c693f497): Add bureau filter for SESP
* 2024-01-30 (84247e5c): Merged PR 797: integrated gender distribution by Bureau and gender breakd won with BE
* 2024-01-30 (41754c48): integrated gender distribution by Bureau and gender breakd won with BE
* 2024-01-30 (1198f69a): Merged PR 257: Deploy
* 2024-01-30 (f4f70ccb): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-30 (4d3bdad0): Merged PR 795: Resolve issues in peoples page
* 2024-01-30 (9839b9fd): Merged PR 796: Top 5 project integration changes in home page
* 2024-01-30 (45922748): Merged PR 256: Delpoy
* 2024-01-30 (80a18704): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-30 (3d38eaf2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-350-ui
* 2024-01-30 (77573469): top 5 project integration changes in home page
* 2024-01-30 (4f15ba80): remove console log
* 2024-01-30 (c99b8480): Merged PR 794: Section descripiton changes for resource mobilization, total contributions an...
* 2024-01-30 (434aa616): Resolve gender parity issue
* 2024-01-30 (e5bf596b): Section descripiton changes for resource mobilization, total contributions and delivery
* 2024-01-30 (4446701b): Update key card scores
* 2024-01-29 (adc6da8a): Merged PR 255: Deploy
* 2024-01-29 (cf9494c1): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-29 (3e044c7a): Merged PR 793: normalized values for 100
* 2024-01-29 (688bca21): normalized values for 100
* 2024-01-29 (680c94b0): Merged PR 254: remove indicator score
* 2024-01-29 (c88022e5): remove indicator score
* 2024-01-29 (2b24c744): Merged PR 253: Deploy
* 2024-01-29 (1d912f1b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-29 (1dc18c37): change gender parity
* 2024-01-29 (6c8e4df4): Changes
* 2024-01-29 (2120c722): Merged PR 792: Add gender parity related stats
* 2024-01-29 (9c0e34d2): Add names to filenames
* 2024-01-29 (e75639ab): Add country filter for gender parity
* 2024-01-29 (34e11ec7): Add gender distribution
* 2024-01-29 (78458d83): Merged PR 790: integrated PEOPLE\_ENGAGEMENT\_INDEX with BE
* 2024-01-29 (696b351d): integrated PEOPLE\_ENGAGEMENT\_INDEX with BE
* 2024-01-29 (5c1c8681): Merged PR 789: Add engagement to nav stats
* 2024-01-29 (ed1dbca2): Add engagement to nav stats
* 2024-01-29 (21598ab6): Merged PR 788: Resolve lint issues
* 2024-01-29 (592ed0e4): Resolve lint issues
* 2024-01-29 (973811e5): Merged PR 787: Completed engagement index
* 2024-01-29 (c87ee9a8): Completed engagement index
* 2024-01-29 (074cb7a6): Merged PR 784: text-changes
* 2024-01-29 (efa63dd1): Merged PR 785: Gender parity indicator score fixes
* 2024-01-29 (c2e81a62): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-346
* 2024-01-29 (6443c819): gender parity fixes
* 2024-01-29 (e8ca1e63): text-changes
* 2024-01-29 (89adfb54): fixed issue in value not formatted in irrf % completion
* 2024-01-29 (a085dd1b): Merged PR 781: fixed issues in indicator score mismatch issues
* 2024-01-29 (a3cd4934): Merged PR 782: Change object attribute order
* 2024-01-29 (a0b1de86): updated scoreMethodology for VALUES\_SESP
* 2024-01-29 (23558d2d): Change object attribute order
* 2024-01-29 (05b92da7): fixed issues in indicator score mismatch issues
* 2024-01-29 (d3528513): Merged PR 780: Rename the filename
* 2024-01-29 (28558931): Rename the filename
* 2024-01-29 (6bee2c35): Merged PR 778: Resolve vacancy rate file issue
* 2024-01-29 (fd20369c): Merged PR 779: gender parity integrations
* 2024-01-29 (88c5e11c): gender parity integrations
* 2024-01-26 (dc32b6c8): Resolve vacancy rate file issue
* 2024-01-26 (342f78e2): Merged PR 777: Resolve lint issue
* 2024-01-26 (8b0f1aa0): Resolve lint issue
* 2024-01-26 (3dfc9dd8): Merged PR 776: Add gender parity indicator and vacancy
* 2024-01-26 (02e43ad0): Add gender parity indicator and vacancy
* 2024-01-26 (6ceb5b98): Merged PR 252: Deploy
* 2024-01-26 (46e95694): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-26 (328499ce): Merged PR 774: vacancy rate color methodology change
* 2024-01-26 (97451702): vacancy rate color methodology change
* 2024-01-26 (886d746a): Merged PR 773: Pipeline anlaytics fixes
* 2024-01-26 (203ad8a0): Merged PR 772: Added manualCountryEntry option in project map
* 2024-01-26 (d08dff8f): removed unnecessary console.log
* 2024-01-26 (e415420f): CO pipeline changes
* 2024-01-26 (53cf0934): kosova country issue fixes
* 2024-01-26 (7f3172c5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-26 (8a62c8dc): Add dynamic vacancy data
* 2024-01-26 (bf102213): Merged PR 770: dynamic text changes efficiency cumulative average
* 2024-01-26 (2800fa8d): dynamic text changes efficiency cumulative average
* 2024-01-26 (e7d93022): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-co-map-fixes
* 2024-01-26 (76b3bc2d): Merged PR 769: changes
* 2024-01-26 (c329d06e): changed global country rank to average sized agreement
* 2024-01-26 (0731a457): did text changes, card organize and overflow bug in IFD inner page
* 2024-01-26 (701d7efb): fixed some issues in CO country page
* 2024-01-24 (58d352c5): added manualCountryEntry option in project map
* 2024-01-24 (9d89337d): Merged PR 768: fixed efficiency page rerendering and tooltip rerendering
* 2024-01-24 (f549757b): removed unnecessary console.log
* 2024-01-24 (42b70251): fixed issue in tooltips rerendering in Efficiency page
* 2024-01-24 (d0b31061): fixes in calculating the max zoom level for CO page countries
* 2024-01-24 (e9c7dd56): Merged PR 767: Add description to top 5 projects
* 2024-01-24 (bd6b4aa8): Change function name
* 2024-01-24 (a74535d2): Add description to top 5 projects
* 2024-01-24 (7bb2c873): Merged PR 765: Name of the Downloaded File fixes
* 2024-01-23 (e6cf2334): Name of the Downloaded File fixes
* 2024-01-23 (7f8d94a4): Merged PR 764: added min height for stat chards
* 2024-01-23 (e01e020d): added min height for stat chards
* 2024-01-23 (db8ccfd7): Merged PR 763: connected targets of contributions and institutional resources
* 2024-01-23 (e9e1b760): connected targets of contributions and institutional resources
* 2024-01-22 (9f67b446): Merged PR 251: Update gender score
* 2024-01-22 (60f1a441): Update gender score
* 2024-01-22 (29245b9f): Merged PR 250: Deploy
* 2024-01-22 (e99fb24c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (1dae91cb): Merged PR 761: custom track text for contributions and institutional resources
* 2024-01-22 (0ae0640e): updated
* 2024-01-22 (bba23be2): resolved merge conflict
* 2024-01-22 (5a7d5b42): custom track text for contributions and institutional resources
* 2024-01-22 (ebe8d031): Merged PR 249: Deploy
* 2024-01-22 (22ad8730): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (1a0cce75): Merged PR 760: minor fixes
* 2024-01-22 (a8a33a2d): minor fixes
* 2024-01-22 (94ef00ad): Merged PR 248: Deploy
* 2024-01-22 (0ebd0269): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (bfca39bf): Merged PR 758: SESP last updated date format fix
* 2024-01-22 (3da7c48c): SESP last updated date format fix
* 2024-01-22 (9cde1a0d): Merged PR 247: Deploy
* 2024-01-22 (4bc67460): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (77f77b9a): Merged PR 756: minor fixes
* 2024-01-22 (8fb8efca): minor fixes
* 2024-01-22 (1c724e15): Merged PR 246: Deploy
* 2024-01-22 (d9b7d4da): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (ba0e1b18): Remove toFixed
* 2024-01-22 (97c0a930): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (6993578d): Fix lint issue
* 2024-01-22 (e738ed18): SESP issue
* 2024-01-22 (eaebdced): Update not monitored
* 2024-01-22 (a5f17763): Merged PR 245: Deploy
* 2024-01-22 (dd0e5c90): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (a21eed1f): Merged PR 754: removed donors col in top5 project
* 2024-01-22 (52929f9b): removed donors col in top5 project
* 2024-01-22 (2dfd5810): Merged PR 751: added tooltip to sesp graph
* 2024-01-22 (262a4e71): fixed score mismatch issue
* 2024-01-22 (18114f6c): ui fixes
* 2024-01-22 (54621c13): Merged PR 752: country coordinates added
* 2024-01-22 (cabf625b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-co-map-fixes
* 2024-01-22 (65163273): country coordinates added
* 2024-01-22 (cd184394): Merged PR 244: Deploy
* 2024-01-22 (3b571c34): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-22 (099e72e4): removed unnecessary lorem ipsium
* 2024-01-22 (e4b200c3): added tooltip to sesp graph
* 2024-01-22 (1e5bfa57): Merged PR 749: High Risk Project data integration from BE
* 2024-01-22 (ddc9dfc3): Fix QA SESP Score
* 2024-01-22 (548d2a2a): removed view more
* 2024-01-22 (7a2fc4d6): resolved merge conflict and values page changes
* 2024-01-22 (775ae582): map data mapper
* 2024-01-22 (79f06975): integrated global progress card with BE
* 2024-01-22 (5b293cc1): Bug fix for QA
* 2024-01-22 (96984fc1): Add unified id
* 2024-01-22 (4c22b08f): Fix QA stat issue
* 2024-01-22 (2f17222e): get Unified unique count
* 2024-01-22 (c1f5c520): Merged PR 747: top 5 projects stat fixes
* 2024-01-22 (6aedf9b1): revert change
* 2024-01-22 (d2c74c9d): top 5 projects stat fixes
* 2024-01-22 (99b1d4f1): QA and SESP change
* 2024-01-22 (59f218b8): Merged PR 746: SESP graph and indicator score
* 2024-01-22 (94bb84bc): Add Extempted
* 2024-01-22 (3d0321fb): integrated with BE
* 2024-01-22 (5def3ae5): Add to completion
* 2024-01-22 (4d73f29a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into SESP-graph
* 2024-01-21 (96f9e1b4): add QA even without country
* 2024-01-21 (e625aee0): Add title for Funding
* 2024-01-21 (e245d158): new value add
* 2024-01-21 (e55dccd5): Update to previous
* 2024-01-21 (a342abeb): add log line
* 2024-01-21 (b6988703): Update country data
* 2024-01-21 (080a998f): Merged PR 243: Deploy
* 2024-01-21 (6b8614d1): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-21 (5bc0a81b): Fix overall score
* 2024-01-21 (3e5be069): Merged PR 745: Change key stat calculation methodology
* 2024-01-21 (66579342): Change key stat calculation methodology
* 2024-01-21 (7ff4b97e): Fix completion ratio
* 2024-01-21 (a67c9e38): Fix QA rate issue
* 2024-01-21 (0a07d620): Fix graph data
* 2024-01-21 (e02d47a0): Pipeline stat
* 2024-01-21 (b8bec405): Revert hardcoded config
* 2024-01-21 (0789f75b): Add funding stream
* 2024-01-21 (bad5032c): Pipeline changes
* 2024-01-20 (4402b2d6): Merged PR 741: resolve issues in key stats
* 2024-01-21 (6ad73df5): resolve issues in key stats
* 2024-01-20 (2fbc6b00): Merged PR 740: Add key stats for qa and sesp
* 2024-01-21 (88b98e98): Change key stats
* 2024-01-21 (53f2d8bd): Add sesp indicator
* 2024-01-20 (aaa7e262): Revert config
* 2024-01-20 (858dc3d3): Fix issues
* 2024-01-20 (92d42547): Merged PR 737: Change qa indicator
* 2024-01-20 (df5a39cb): Change qa indicator
* 2024-01-20 (f3987126): Merged PR 242: Deploy
* 2024-01-20 (2ab9b4a2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-20 (852cb31f): If exist
* 2024-01-20 (d68c463a): round to 2
* 2024-01-20 (729c7dc4): Merged PR 241: Deploy
* 2024-01-20 (f227c51e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-20 (1ea67a1e): Pipeline issues
* 2024-01-20 (6331e8b0): Merged PR 240: Deploy
* 2024-01-20 (e2e4f796): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-20 (e2f2d10f): remove %
* 2024-01-20 (3e57afbc): Merged PR 735: Add new indicators
* 2024-01-20 (f504f1cd): rename files
* 2024-01-20 (1836fd2e): Add new indicators
* 2024-01-20 (2c422a43): Merged PR 239: Deploy
* 2024-01-20 (f785958c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-20 (2dd14cad): Change positions
* 2024-01-20 (80775867): Update text changes
* 2024-01-19 (774c8fd5): Merged PR 238: Deploy
* 2024-01-19 (f9b10996): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-19 (e240aabc): Merged PR 731: resource mobilization stat cards
* 2024-01-19 (027390fb): resource mobilization stat cards
* 2024-01-19 (7f77a2f3): Merged PR 729: integrated pipeline analytics with BE
* 2024-01-19 (b175b8c1): resolved merge conflict
* 2024-01-19 (29bc23d7): Merged PR 730: map load issue changes and total contribution fixes
* 2024-01-19 (8785f2aa): map load issue changes and total contribution fixes
* 2024-01-19 (1c853c73): Change prject file handler
* 2024-01-19 (44f433aa): Merged PR 237: Deploy
* 2024-01-19 (312e914f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-19 (59441314): integrated with BE
* 2024-01-19 (c8dcb7bd): Merged PR 727: total contribution stat changes
* 2024-01-19 (c7a27028): Merged PR 728: Change query
* 2024-01-19 (d66ea999): resolve lint issues
* 2024-01-19 (0a87a6e2): Change query
* 2024-01-19 (5b1fb300): total contribution stat changes
* 2024-01-19 (0b97c33d): Merged PR 726: Add new indicators
* 2024-01-19 (77941072): change the triger time
* 2024-01-19 (d82d6624): change the query
* 2024-01-19 (4ae9f5f9): Change query
* 2024-01-19 (77fce3c0): Add new indicators
* 2024-01-19 (3ad36fd3): Merged PR 236: Deploy
* 2024-01-19 (d1d535ce): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-19 (636b9920): Merged PR 724: link to the individual CO page on Transparency Portal
* 2024-01-19 (d1c58b40): Merged PR 725: "i" Tooltip Hand Icon change
* 2024-01-19 (7250a7ad): "i" Tooltip Hand Icon change
* 2024-01-19 (8b7a51f3): updated
* 2024-01-19 (f3a037e0): link to the individual CO page on Transparency Portal
* 2024-01-19 (0b97fe76): Merged PR 723: CO page target stats fixes
* 2024-01-19 (a86aab95): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-318-changes
* 2024-01-19 (b69bc503): cum avg CO page fixes
* 2024-01-19 (70e05821): home page total contribution stat fixes
* 2024-01-19 (b134a0b5): Merged PR 722: removed view indicator btn and added link to methodology btn
* 2024-01-19 (9df14e37): removed view indicator btn and added link to methodology btn
* 2024-01-18 (abe73da4): Merged PR 717: CO capacity further changes
* 2024-01-18 (2870232c): Merged PR 235: Deploy
* 2024-01-18 (6485c3a7): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-18 (07affb5c): Merged PR 719: efficiency chart fixes
* 2024-01-18 (f4dabcc5): Merged PR 720: Change query
* 2024-01-18 (d14b88d4): Change query
* 2024-01-18 (6333a64d): cum avg chart fixes
* 2024-01-18 (d4f8cfdd): live chart fixes
* 2024-01-18 (59366fb1): Merged PR 718: Update query to read efficiency data
* 2024-01-18 (0397c300): Update query to read efficiency data
* 2024-01-18 (ddc15b49): CO capacity further changes
* 2024-01-18 (9e819b57): Merged PR 715: cpd management page fixes and changes
* 2024-01-18 (5e3aa2ee): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-294-ui
* 2024-01-18 (22a4b4a5): cpd management page changes
* 2024-01-18 (d42cdfa7): Merged PR 714: updated cards for globe section
* 2024-01-18 (3dff0552): intermediate files
* 2024-01-18 (a475e730): updated cards for globe section
* 2024-01-18 (217cc309): Merged PR 711: updated tooltip location in overview page
* 2024-01-17 (a2947d44): Merged PR 234: Deploy
* 2024-01-17 (f193c932): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-17 (333118ee): Merged PR 712: cdpManagement page changes
* 2024-01-17 (bab9c67c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-294-ui
* 2024-01-17 (a0a8fa3f): cpd management changes
* 2024-01-17 (3310de83): updated
* 2024-01-17 (3772567e): Merged PR 710: Add SF\_UNITY\_OPPORTUNITY stats
* 2024-01-17 (c817fb0c): Add source of the unity file
* 2024-01-17 (7d9781c6): Add SF\_UNITY\_OPPORTUNITY stats
* 2024-01-17 (1695393d): Merged PR 709: changed tooltip behaviour
* 2024-01-17 (1bd64bf7): updated the tooltips to new tooltip
* 2024-01-17 (7607b7f1): Merged PR 707: updated
* 2024-01-17 (26e0a1c7): updated
* 2024-01-17 (073b55ef): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-294-ui
* 2024-01-16 (dd6545f7): Merged PR 233: Deploy
* 2024-01-16 (b9c85a01): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-16 (083a5d7b): Merged PR 704: Resolve last updated date issue
* 2024-01-16 (aef86667): Update queery
* 2024-01-16 (b32ea1c2): Merged PR 705: fixed issue in revenue graph
* 2024-01-16 (7cf42ccd): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-16 (f65937b5): fixed issue in revenue graph
* 2024-01-16 (a018bfd7): Merge branch 'develop' into bug/file-updated-data
* 2024-01-16 (8ba275a6): Resolve last updated date issue
* 2024-01-16 (be1cdbd1): added basic callout component
* 2024-01-16 (96bdb15c): added cpd management section
* 2024-01-16 (45d93579): Merged PR 702: home page map component changes
* 2024-01-16 (588ccd11): home page map component changes
* 2024-01-16 (651808b6): Merged PR 701: project\_list file handler changes
* 2024-01-16 (226b3599): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-293-changes
* 2024-01-16 (1726b33e): project\_list file handler changes
* 2024-01-16 (f1b7fd67): Merged PR 700: fixed issues in homepage notecard and signature solutions filter
* 2024-01-16 (7315f750): fixed issue in signature solutions filters
* 2024-01-16 (0a90dc17): fixed issue in height mismatch in homepage note card
* 2024-01-16 (225e5a82): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-293-changes
* 2024-01-12 (8d9c1b77): Merged PR 232: Deploy
* 2024-01-12 (82e98643): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-12 (9800367f): Merged PR 698: updated the data source and last updated time for charts
* 2024-01-12 (73b1cc1b): updated the data source and last updated time for charts
* 2024-01-12 (c65a69f4): Merged PR 697: Fix audit indicator issue
* 2024-01-12 (ce2feb29): Merged PR 231: Deploy
* 2024-01-12 (33d473b4): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-12 (b0f0b014): Fix audit indicator issue
* 2024-01-12 (79e92143): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-293-changes
* 2024-01-12 (3147f0eb): Merged PR 692: Add country filter for maps
* 2024-01-12 (bfb8c422): resolve lint issues
* 2024-01-12 (3241e688): Merged PR 694: Fixed issues with navigating and navigating to values page on sesp click
* 2024-01-12 (d5c158cc): Add metadata for all indicators
* 2024-01-12 (441bfe36): Merged PR 695: Tooltip title changes
* 2024-01-12 (5e1cf81e): tooltip title changes
* 2024-01-12 (23806082): merged dev
* 2024-01-12 (4f1eda96): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into minor-changes
* 2024-01-12 (eac16599): project map component changes
* 2024-01-12 (0eccfd2e): fixed navigating issues
* 2024-01-12 (5dc5bec6): updated
* 2024-01-12 (35363cc4): Merged PR 691: download zip folder changes
* 2024-01-12 (84e068ff): Change texts
* 2024-01-12 (acb8a145): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-254-ui
* 2024-01-12 (b4f3ec6b): Merged PR 690: updated title change
* 2024-01-12 (f5c83f5c): minor text changes
* 2024-01-12 (70e233f3): Add country filter for maps
* 2024-01-12 (f59a6a61): updated
* 2024-01-12 (e1b82a5e): updated comments
* 2024-01-12 (f1d4f988): download zip folder changes
* 2024-01-12 (4820bccb): made the cross in cummulative avg bigger
* 2024-01-12 (00344640): updated
* 2024-01-12 (89cc3435): Merged PR 688: changed the title for SESP
* 2024-01-12 (f90a0bb3): changed the title for SESP
* 2024-01-11 (f471436a): Merged PR 230: Deploy
* 2024-01-11 (62de7a38): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-11 (6ba524a2): Merged PR 685: Tooltip content changes for main pages
* 2024-01-11 (552d5422): conflict fixes
* 2024-01-11 (f847b9ce): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-296-ui
* 2024-01-11 (94e7c12c): Merged PR 686: report cards section added missing cards
* 2024-01-11 (e5d3daf8): report cards section added missing cards
* 2024-01-11 (20027341): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-296-ui
* 2024-01-11 (48ad5401): Merged PR 684: changes for perf-295, perf-297, perf-298, perf-299
* 2024-01-11 (6bc9deaa): Tooltip content changes for main pages
* 2024-01-11 (1c91ab0e): updated font size
* 2024-01-11 (25c4de39): CO changes
* 2024-01-11 (5d4f97bc): added tooltip for global score
* 2024-01-11 (01889ac8): Merged PR 682: last updated time changes
* 2024-01-11 (9a0edad0): Merged PR 683: HomePage filter
* 2024-01-11 (244e1021): made header scores text size bigger
* 2024-01-11 (457bda94): resolved merge conflict
* 2024-01-11 (3cd338f3): integrated global filter to graphs
* 2024-01-11 (b0aa15da): last updated time changes
* 2024-01-10 (ec0327a7): Merged PR 228: Deploy
* 2024-01-10 (c45165e7): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-10 (29380fdc): Merged PR 681: Top 10 Countries Delivery fix
* 2024-01-10 (899d0db3): Top 10 Countries Delivery fix
* 2024-01-10 (a5dcddb3): Merged PR 227: Deploy
* 2024-01-10 (850b6e23): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-10 (f3bda4fa): Merged PR 679: Fix the data issue
* 2024-01-10 (e5b9a50f): Fix the data issue
* 2024-01-10 (b9e30ff2): Merged PR 677: fixed delivery issue
* 2024-01-10 (79fd0b4d): update url
* 2024-01-10 (26f1ae34): fixed delivery issue
* 2024-01-10 (aba77385): Merged PR 226: Deploy
* 2024-01-10 (d735ea7a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-10 (3a39e19d): Merged PR 675: Download Data changes
* 2024-01-10 (b5208ce7): Data download changes
* 2024-01-10 (87735748): Download Data changes
* 2024-01-10 (efe6a17e): Merged PR 673: New Country Office Home Page - Total Contributions integrations
* 2024-01-10 (8aedbdac): Merged PR 671: Updated queries
* 2024-01-10 (7cd95968): last updated time added in accountability page
* 2024-01-10 (8d220e49): New Country Office Home Page - Total Contributions integrations
* 2024-01-10 (8228ea2f): Updated queries
* 2024-01-10 (4bcd43cb): Merged PR 670: Last Updated Data Warehouse Date on for delivery datas changes
* 2024-01-10 (9a2876d8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-286
* 2024-01-10 (cc382656): Last Updated Data Warehouse Date on for delivery datas changes
* 2024-01-09 (e29e4eff): Merged PR 225: Deploy
* 2024-01-09 (30e0df66): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-09 (2f267708): Merged PR 668: info-icon shrinked in some sections fixed
* 2024-01-09 (f1230d51): Merged PR 669: Add metadata for efficiency and audit pages
* 2024-01-09 (0a8c845c): Add metadata for efficiency and audit pages
* 2024-01-09 (671aa4cf): updated info icon size so that it wont get shrinked
* 2024-01-09 (4edf54b2): Merged PR 666: Delivery stats fixes
* 2024-01-09 (28b470ff): Merged PR 665: Completed data download option
* 2024-01-09 (94d57d13): Delivery stats fixes
* 2024-01-09 (36deb224): Merged PR 664: getting data from the BE for country performance cards
* 2024-01-09 (a1a75aa8): Completed data download option
* 2024-01-09 (76683d06): getting data from the BE for country performance cards
* 2024-01-09 (026233bb): updated
* 2024-01-09 (af84078a): Merged PR 663: score issue and space between pie chart side labels
* 2024-01-09 (b51fcef2): Merged PR 662: Change expiration time
* 2024-01-09 (f14d0c3f): Change expiration time
* 2024-01-09 (92086cc8): added space between title and pie side labels graphs
* 2024-01-09 (d7790aa5): fixed issue with score mismatches
* 2024-01-09 (1f882b92): Merged PR 661: Add data download option
* 2024-01-09 (5df327ec): resolve lint issues
* 2024-01-09 (cab31343): Add data download option
* 2024-01-09 (8d1f8bbb): Merged PR 659: font-issue
* 2024-01-09 (9a91e257): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into font-issue
* 2024-01-09 (93d13750): font files added
* 2024-01-09 (8812096b): Merged PR 658: Gauge component color issue fixes
* 2024-01-09 (ce807258): Gauge component color issue fixes
* 2024-01-09 (eb36c148): Merged PR 657: Tooltip changes - Country Office Capacity Index
* 2024-01-09 (d3fe2c77): Tooltip changes - Country Office Capacity Index
* 2024-01-08 (d2ef966a): Merged PR 655: added global storage and improved data retrieval from BE
* 2024-01-08 (0a498e8f): resolved merge conflict
* 2024-01-08 (26d790a6): fixed issue in not scrolling to top
* 2024-01-08 (0a2e1306): Merged PR 224: Deploy
* 2024-01-08 (c314a924): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-08 (38705a30): Merged PR 653: Country Office Capacity + INFORM Index fixes
* 2024-01-08 (3869e796): Country Office Capacity + INFORM Index fixes
* 2024-01-08 (73f5f9fc): created GetDataContext and global state management for data
* 2024-01-08 (c5604e37): Merged PR 651: HOME\_CAPACITY\_MATRIX stat changes
* 2024-01-08 (bfe5f64d): HOME\_CAPACITY\_MATRIX changes
* 2024-01-08 (b43aedb5): HOME\_CAPACITY\_MATRIX stat changes
* 2024-01-08 (3a76984a): Merged PR 650: color methodology refactoring
* 2024-01-08 (f884ecc0): color methodology refactoring
* 2024-01-05 (1e250a0d): Merged PR 647: removed company field in tooltips in engagement history graph and fixed some ui issues
* 2024-01-05 (fb2d9994): updated
* 2024-01-04 (b3096fcc): Updated azure-pipelines-web.yml
* 2024-01-04 (a337df9d): Updated ConnectionContext.tsx
* 2024-01-04 (93275f93): Merged PR 223: Deploy
* 2024-01-04 (03600abd): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-04 (3d8db9e2): Merged PR 645: textColorGauge updated
* 2024-01-04 (84e1d9c5): textColorGauge updated
* 2024-01-04 (3917c3d5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-04 (3fd7f9ed): Merged PR 644: Changes to Home Page Barometer
* 2024-01-04 (484dd03f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-277-ui
* 2024-01-04 (486ad14f): Changes to Home Page Barometer
* 2024-01-04 (65361f88): Merge branch 'develop'
* 2024-01-04 (c675125c): Merged PR 221: Deploy
* 2024-01-04 (d89719ad): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-04 (84adec22): Merged PR 643: changes
* 2024-01-04 (39003aa3): updated
* 2024-01-04 (38915eb7): changes
* 2024-01-04 (5664a747): Merged PR 642: Resolve decimal point issues
* 2024-01-04 (02c603f2): Merged PR 641: added institutional resources card in home page
* 2024-01-04 (d0ab1612): update IFD description text
* 2024-01-04 (1a899fbc): Resolve decimal point issues
* 2024-01-04 (4fe2fe49): added institutional resources card in home page
* 2024-01-04 (e6c54886): Merged PR 220: Deploy
* 2024-01-04 (f8084506): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-04 (683c41dd): Merged PR 637: changes info icon size, text changes and global key area changes
* 2024-01-04 (2efda4b2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into new-mobile-responsive
* 2024-01-04 (2af55d0e): updated
* 2024-01-04 (f2bb4173): Merged PR 635: Home page stats integrations
* 2024-01-04 (157dcb48): Merged PR 638: Card text updates
* 2024-01-04 (a86fbceb): Merged PR 636: Add country filter for IRRF
* 2024-01-04 (7f1faea9): resolved merge conflict and fixed ui issue in CO capacity cards
* 2024-01-04 (140f0190): Card text updates
* 2024-01-04 (c48f1450): change global progress of key areas
* 2024-01-04 (26c641ca): made the info icon larger and updated text
* 2024-01-04 (e3f8fe0e): Add country filter for IRRF
* 2024-01-04 (1ed1450e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-250-ui
* 2024-01-04 (650263e6): Home page stats integrations
* 2024-01-04 (b4a3b469): Merged PR 634: changed globe spinning direction and reduced spinning speed
* 2024-01-04 (af15b702): changed globe spinning direction and reduced spinning speed
* 2024-01-03 (9f0cb2c3): Merged PR 219: Deploy
* 2024-01-03 (03f4d84f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-03 (e6cd2770): Merged PR 632: cum avg fixes
* 2024-01-03 (52aeb849): cum avg fixes
* 2024-01-03 (a2c80250): Merged PR 217: Deploy
* 2024-01-03 (a535de6b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-03 (8a97d05b): Merged PR 631: Minor changes
* 2024-01-03 (4fdf4612): Merged PR 630: Resolve issue in PERF-164
* 2024-01-03 (20f77d15): changed resource mobilization to contributions
* 2024-01-03 (30255933): removed decimals in CO Audit Rating table
* 2024-01-03 (fd059fe7): Change name
* 2024-01-03 (d0a91750): Change processor for delivery file
* 2024-01-03 (826ea41d): Merged PR 216: Deploy
* 2024-01-03 (307553bd): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-03 (4736cef3): changed legend in IFD
* 2024-01-03 (45f94521): Merged PR 628: Text changes for charts
* 2024-01-03 (9d5e65fe): Merged PR 627: Resolve delivery data cumulative avg isssue
* 2024-01-03 (65189425): Text changes for charts
* 2024-01-03 (a3741b0c): Merged PR 625: fixed paddings in pages and wrong data in engagement history graph
* 2024-01-03 (923df953): Resolve delivery data cumulative avg isssue
* 2024-01-03 (618175a5): fixed issue in not showing correct data for engagement history
* 2024-01-03 (bc399bcd): moved from ms-grid to tailwind grid and fixed paddings in sub pages
* 2024-01-03 (eda91353): Merged PR 624: map component - disabled dropdown
* 2024-01-03 (fd2ed86f): Merged PR 623: Update Greening Moonshot Text
* 2024-01-03 (a89e4148): fixed paddings of pages
* 2024-01-03 (8bcda221): map component - disabled dropdown
* 2024-01-03 (ef938cae): fixed issue in fitler icon getting small on smaller screens
* 2024-01-03 (0f623b99): Merged PR 215: Deploy
* 2024-01-03 (79f37f3e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-03 (4e4d1145): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-250-ui
* 2024-01-03 (9d8ed19b): Update Greening Moonshot Text
* 2024-01-03 (07bc0e08): Merged PR 622: CHange the apiUrl for getting country coordinates
* 2024-01-03 (42572936): Merged PR 620: file changes
* 2024-01-03 (d3e65209): CHange the apiUrl for getting country coordinates
* 2024-01-03 (5a9e2ef9): Merged PR 621: fixed issue with filters, when closing filters in mobile screen getting while...
* 2024-01-03 (882d3d9b): fixed issue with filters, when closing filters in mobile screen getting while blank screen sometimes
* 2024-01-03 (eb35f3cf): Merge branch 'develop' into PERF-260
* 2024-01-02 (12c10b18): resolve stat card issues
* 2024-01-02 (468c47b3): integrated efficiency stat cards
* 2024-01-02 (2c594019): add null checks
* 2024-01-02 (d4bf8776): Refactor processor
* 2024-01-02 (477bffd1): Merged PR 619: new map component fixes for tooltip and dynamic zoom level
* 2024-01-02 (2e79218b): new map component fixes for tooltip and dynamic zoom level
* 2024-01-02 (5e21692c): Merged PR 618: added border radius to tooltip
* 2024-01-02 (87aecd6a): added border radius to tooltip
* 2024-01-02 (88fb0f69): Merged PR 617: updated globe selection tooltip and fixed some issues in global prgress card section
* 2024-01-02 (08844b1a): removed unnecessary console.log
* 2024-01-02 (6b8df9a5): resolved merge conflict
* 2024-01-02 (175b39f9): updated
* 2024-01-02 (bc837dbd): fixed issue in key areas in global progress card
* 2024-01-02 (b822e156): Add stat cards
* 2024-01-02 (4c1d5f9f): improved the globe selection tooltip
* 2024-01-02 (560038a6): resolve sorting issue
* 2024-01-01 (a7f740c9): Merged PR 214: Deploy
* 2024-01-01 (f34c2702): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2024-01-01 (2d296549): Merged PR 615: Fixed the mapcomponent issue regarding the undefined coordinates
* 2024-01-01 (b591d81b): Merge branch 'perf-cum-avg-fixes' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-262-ui
* 2024-01-01 (ee3776bc): fixed the mapcomponent issue regarding the undefined coordinates
* 2024-01-01 (060580af): Merged PR 612: added sorting to the new tables
* 2024-01-01 (8c10d85b): Merged PR 613: fixed the duplicate map component issue and added custom style for the new ma...
* 2024-01-01 (4a7465b7): Merged PR 611: resolve date issue
* 2024-01-01 (984bcb86): Add ranking for co-performance
* 2024-01-01 (169f3728): fixed the duplicate map component issue and added custom style for the new map component
* 2024-01-01 (b239ddc8): added sorting to the new tables
* 2024-01-01 (2fecbe14): resolve date issue
* 2024-01-01 (e7056df0): Change carbonData
* 2024-01-01 (619f4696): Merged PR 610: New map component changes
* 2024-01-01 (ec153728): new map component changes
* 2024-01-01 (e61c268c): home page new map component changes

## 2023

### December

* 2023-12-29 (ca43e40a): Merged PR 609: maps and pie charts are centered on mobile screens and changed the info icon shape rendering
* 2023-12-29 (4a562708): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into new-mobile-responsive
* 2023-12-29 (65b6e155): info icon blurry issue
* 2023-12-29 (276de8eb): Remove unwanted filters
* 2023-12-29 (6780ee32): Remove null values in the country column
* 2023-12-29 (704706ab): Add filtering option for stat cards
* 2023-12-29 (60e7a3f7): pie charts in the centered on mobile screens
* 2023-12-29 (d22c8978): map centering on mobile devices
* 2023-12-28 (dfcfe19e): Merged PR 213: Deploy
* 2023-12-28 (eec2b7b7): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-28 (3e7c6cc7): Merged PR 608: fixed padding issues and incorrect tooltip issue
* 2023-12-28 (2d576e3e): resolved merge conflict
* 2023-12-28 (3923f0f7): fixed issue in incorrect tooltips
* 2023-12-28 (61c94a5b): fixed issues in paddings and positions in global filter
* 2023-12-28 (fcbf8e4c): Merged PR 607: Refactor cumulative delivery
* 2023-12-28 (a95c39fa): Change triger time
* 2023-12-28 (2b4e184c): Refactor cumulative delivery
* 2023-12-28 (70b74fe3): Merged PR 594: File structure changes
* 2023-12-28 (6d46df2f): update files
* 2023-12-28 (bfe2c870): remove comments
* 2023-12-27 (376b4c15): Merged PR 212: Deploy
* 2023-12-27 (fa5f5190): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-27 (9a4aef04): Merged PR 605: Download data changes for sub sections
* 2023-12-27 (b80a784f): Download data changes for sub sections
* 2023-12-27 (851f8361): Merged PR 211: Deploy
* 2023-12-27 (bb3bd791): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-27 (d15971a6): Merged PR 603: updated engagement index indicator scores
* 2023-12-27 (b593a37f): updated engagement index indicator scores
* 2023-12-23 (3f63c2ae): Completed changes
* 2023-12-23 (1bf3e867): Add delivery filter
* 2023-12-23 (dd95394f): Chage trigger time
* 2023-12-22 (a7d6acf4): Merged PR 210: Deploy
* 2023-12-22 (f5229a5a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-22 (a60bd58f): Merged PR 601: Download data changes
* 2023-12-22 (2740f222): Merged PR 600: Basic funnel chart and people dummy data change
* 2023-12-22 (87e3026c): Merge branch 'country-pages' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-254-ui
* 2023-12-22 (9dc2c2db): download data changes
* 2023-12-22 (8e2930ad): made the changes to people dummy data
* 2023-12-22 (ddd0a7fd): basic funnel chart added
* 2023-12-22 (6008bbf2): Change datacube triggers
* 2023-12-22 (c6a136ff): Add country filters
* 2023-12-22 (1185d09a): Merge branch 'update-filters' into PERF-253
* 2023-12-21 (1e75adcf): Merged PR 209: Deploy
* 2023-12-21 (95c5ad5c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-21 (32615f7d): Merged PR 598: moved the components in sub pages into new tailwind UI design, fixed some UI inconsistencies and integrated global filter with BE
* 2023-12-21 (7a55435a): resolved merge conflict
* 2023-12-21 (14b5489a): removed notecard border
* 2023-12-21 (54717d85): moved components to new tailwind UI design
* 2023-12-21 (736ab46a): Merged PR 597: Remove duplicates
* 2023-12-21 (35449337): Remove duplicates
* 2023-12-21 (b4e529f0): Completed the flow for efficiency
* 2023-12-21 (dfde6821): Complete efficiency
* 2023-12-21 (18d3f8a7): Merged PR 208: Deploy
* 2023-12-21 (89d81440): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-21 (5ee55afa): Merged PR 595: Download data button changes
* 2023-12-21 (9c7d9379): download data button changes
* 2023-12-21 (85887994): Merged PR 593: made change in a key
* 2023-12-21 (4d16c4cd): resolved merge conflict
* 2023-12-21 (8f863b4e): changed border radius of tablegraph and did some refactorings
* 2023-12-21 (fc00b42d): Add tempory changes
* 2023-12-21 (ccdca35a): added tooltips for sub section tablegraph cards
* 2023-12-21 (ccbd1fc9): Merge branch 'country-filter' into PERF-253
* 2023-12-21 (f712e0dd): made change in a key
* 2023-12-21 (0a0f58a1): Merged PR 592: Add test cases for country filter.
* 2023-12-21 (1935bf07): resolve lint issues
* 2023-12-21 (41749000): Add test cases
* 2023-12-21 (c04dafd0): Merged PR 591: Add country filter
* 2023-12-21 (7ea6cfa4): Add country filter
* 2023-12-21 (9eb72ae9): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-254-ui
* 2023-12-21 (dcc266f3): download data tooltip component changes
* 2023-12-20 (91e16265): Merged PR 206: Deploy
* 2023-12-20 (f4dffe2f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-20 (0531d132): Merged PR 589: fixed issue in scrolling, different indicator values and colors, and layout in performance score card
* 2023-12-20 (230b35e2): fixed issues in card heights
* 2023-12-20 (972e2ffc): fixed issue in layout in performance score card section
* 2023-12-20 (e659c5a7): Merged PR 587: filter tags issue fixes for global level filtering
* 2023-12-20 (9adaec06): changed the indicator score
* 2023-12-20 (f385da8b): fixed issue in not getting scrolled in values page
* 2023-12-20 (28da1411): fixed issue in indicator score ranges in transparency index
* 2023-12-20 (6cb51bf2): resolved merge conflict
* 2023-12-20 (2466501e): not allowing to scroll on efficiency page fixed
* 2023-12-20 (4e5058f1): filter tags issue fixes for global level filtering
* 2023-12-20 (94a80669): fixed title change
* 2023-12-20 (04a399fb): Merged PR 586: Add country checkup
* 2023-12-20 (09ebcba5): Add country checkup
* 2023-12-19 (ccc342d5): Merged PR 205: Deploy
* 2023-12-19 (28c19442): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-19 (3dd8c6e6): Merged PR 584: fixed UI issues and added pie chart
* 2023-12-19 (3fac12a0): Merged PR 583: home page global filter view indicator changes
* 2023-12-19 (39976a20): redirecting to pages on view indicator
* 2023-12-19 (1131f432): updated
* 2023-12-19 (205115fa): pipeline funding pie chart added
* 2023-12-19 (61802e78): home page global filter view indicator changes
* 2023-12-19 (61c32ca4): Update deliery mappers
* 2023-12-19 (82026884): fixed some alignement and spacing issue in performance score card section and remove country text from the global filter dropdown
* 2023-12-19 (7edc7079): fixed issue in homepage and global filter styles
* 2023-12-18 (ad938ea0): Merged PR 204: alignment
* 2023-12-18 (bfc115df): Fix verticle middle
* 2023-12-18 (4167ca8c): Merged PR 203: Deploy
* 2023-12-18 (c7bddebe): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-18 (9f8db63d): Merged PR 582: Fixed stat card issue in home page
* 2023-12-18 (bf173cfd): FIxed stat card issue in home page
* 2023-12-18 (b9a12f66): Merged PR 202: Fix header
* 2023-12-18 (26d1ac96): Fix header
* 2023-12-18 (c4e845ef): Merged PR 201: Deploy
* 2023-12-18 (b30f4938): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-18 (ba551177): add styles
* 2023-12-18 (3a768dce): Merged PR 580: Change default value
* 2023-12-18 (7e208ccd): Change default value
* 2023-12-18 (c621a680): Merged PR 200: Deploy
* 2023-12-18 (0934703b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-18 (8bf4a388): fixed the view indicator styles issues
* 2023-12-18 (f3da22b1): Merged PR 578: Home page new component changes
* 2023-12-18 (253ff703): Merged PR 577: remove console logs and add filter data
* 2023-12-18 (e6141288): Merge branch 'global-filter' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-250-ui
* 2023-12-18 (571ccb7b): home page changes
* 2023-12-18 (b40a67f1): updated
* 2023-12-18 (89774d4c): remove console logs and add filter data
* 2023-12-18 (14ad0c0a): updated
* 2023-12-18 (ccf4f307): EFFICIENCY\_PERC\_OF\_TOP\_TEN\_DEL
* 2023-12-18 (0e4b13ce): home page new component changes
* 2023-12-18 (14c542ba): added sections
* 2023-12-18 (37daeba8): Merged PR 576: Add country filter to delivery indicator
* 2023-12-18 (1325f2e0): Add country filter to delivery indicator
* 2023-12-18 (ba033e65): merge changens and updated
* 2023-12-18 (e6aaf4eb): Merge branch 'global-filter' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-250-ui
* 2023-12-18 (8b4944a0): Home page new component changes
* 2023-12-18 (f63aed8f): added global filters
* 2023-12-15 (7997c52e): Merged PR 199: Deploy
* 2023-12-15 (afb5dbf2): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-15 (74ee1fef): Merged PR 575: homePageStat prop changes
* 2023-12-15 (2025db50): homePageStat prop changes
* 2023-12-15 (83a37132): Merged PR 198: Deploy
* 2023-12-15 (f73f51c4): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-15 (b3edd6ac): Merged PR 573: Delivery Indicator Score integrations
* 2023-12-15 (d7d93a9c): Created a separate file for Methodology definitions
* 2023-12-15 (6aed6e8d): Delivery Indicator Score integrations
* 2023-12-15 (2b9e8d53): Merged PR 571: Delivery Score Methodology BE changes
* 2023-12-15 (a47f7b89): Delivery Score Methodology BE changes
* 2023-12-15 (562fb256): added basic select for global filter
* 2023-12-14 (87ef0cc1): Merged PR 197: Deploy
* 2023-12-14 (54f85303): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-14 (ad858fcb): Merged PR 568: added rotationa and fixed style issues
* 2023-12-14 (6e169a45): fixed some alignements
* 2023-12-14 (a08f92ce): added rotationa and fixed style issues
* 2023-12-14 (b756948d): Merged PR 566: Change Order of List in Country Office Audits table data
* 2023-12-14 (68952b4b): Change Order of List in Country Office Audits table data
* 2023-12-14 (d4274e8b): Merged PR 565: Fixed the title issue in the subsection
* 2023-12-14 (7264e68d): Fixed the title issue in the subsection
* 2023-12-13 (a3004f67): Merged PR 196: Deploy
* 2023-12-13 (556effad): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-13 (d0f397ed): Merged PR 563: added basic map globe
* 2023-12-13 (b8d64cce): fixed merge conflict
* 2023-12-13 (73ba48f7): added globe and files for it
* 2023-12-13 (8e15dc9e): added globe
* 2023-12-13 (f4d9608e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-13 (c01f7fb9): Merged PR 561: Bar Chart Race Dynamic Element in efficiency page changes
* 2023-12-13 (171f82ca): added the deleted dummy data file
* 2023-12-13 (bb96ea5a): Bar Chart Race Dynamic Element in efficiency page changes
* 2023-12-13 (07177ddd): Merged PR 560: Update top 10 delivery response structure
* 2023-12-13 (16613e94): uncommented test cases
* 2023-12-13 (3800197b): change test cases
* 2023-12-13 (18a0dbf8): Update response structure
* 2023-12-13 (910531c3): Merged PR 195: Deploy
* 2023-12-13 (8fbb6e40): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-13 (ff429d49): Merged PR 559: Update ifd function
* 2023-12-13 (30fc9962): Update ifd functionality in datacube
* 2023-12-13 (dcbedb08): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-13 (90a07b56): Merged PR 558: changed delivery socre to 100 and removed % from stat cards in home page
* 2023-12-13 (bbd6abb6): Merged PR 557: Update accountability
* 2023-12-13 (fe62ac9c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-13 (25f5cff5): changed delivery socre to 100 and removed % from stat cards in home page
* 2023-12-13 (57a972b6): extended map components to support globe map projection and added style for globe
* 2023-12-12 (b9701453): Update accountability
* 2023-12-12 (1be970b1): Merged PR 556: change in getName function in country\_audit\_mapper func
* 2023-12-12 (26484aca): getName func changes
* 2023-12-12 (b65e5896): fixed getName func
* 2023-12-12 (504b6657): Merged PR 194: Deploy
* 2023-12-12 (d0103233): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-12 (a66accff): Merge branch 'develop' into PERF-241
* 2023-12-12 (7cc254b5): Merged PR 554: update audit changes
* 2023-12-12 (9170bdec): update connenction string
* 2023-12-12 (a3b1528c): update audit changes
* 2023-12-12 (f0789dfd): Merged PR 553: updated
* 2023-12-12 (43b6489c): updated
* 2023-12-12 (370a9fa5): update data structure
* 2023-12-12 (6aa05aed): Merged PR 193: Deploy
* 2023-12-12 (bb60c61a): Merged PR 552: Add top 10 delivery countries
* 2023-12-12 (c62638e5): Add top10 delivery countries
* 2023-12-12 (9abce7ff): Merged PR 550: added filter to SS graph and fixed issue with country filter
* 2023-12-12 (7301a2a6): fixed issue in country filters
* 2023-12-12 (48714105): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into filter-to-signature-solutions
* 2023-12-12 (363b9cb1): added filter for signature solutions
* 2023-12-12 (63b414d7): Merged PR 548: Add reduction percentage
* 2023-12-12 (0c1c6db9): Add reduction percentage
* 2023-12-11 (38b6bdc6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into staging
* 2023-12-11 (1e6d8d7b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-11 (9165de22): Merged PR 546: changed posistion to bottom most
* 2023-12-11 (0f54428a): updated
* 2023-12-11 (5a6a19fe): changed title posistion to bottom most
* 2023-12-11 (e650c174): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-11 (0dc24789): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into staging
* 2023-12-11 (6645e1b9): Merged PR 545: changed title position, changed title of trendline graph, fixed UI issues in audit page
* 2023-12-11 (61ccfa81): fixed ui issues in audit page and table component
* 2023-12-11 (03af50ab): did changes
* 2023-12-11 (7b2e5408): Merge branch 'develop' into staging
* 2023-12-11 (a4ab9670): Merged PR 191: Revert 'Revert 'Deploy''
* 2023-12-11 (872b0bd1): Revert "Revert "Merged PR 188: Deploy""
* 2023-12-11 (3ade1594): Revert "Merged PR 189: Revert 'Deploy'
* 2023-12-11 (941232c1): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-11 (345b3cf4): updated the title posistion and fixed issue with table
* 2023-12-11 (f63cea1e): Merged PR 543: Data cube
* 2023-12-11 (7c68de4f): Merge branch 'develop' into PERF-236
* 2023-12-11 (e85487ef): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-11 (d06af772): Update
* 2023-12-11 (6dcb141e): remove console logs
* 2023-12-11 (600c9ac3): eresolve lint issue
* 2023-12-11 (782e4d20): Add impact ss filters
* 2023-12-11 (6b811ab0): Merged PR 542: Changes for view full indicator button hover effects
* 2023-12-11 (dad999a0): Changes for view full indicator button hover effects
* 2023-12-11 (d766c6f8): Add new methodolgy for greening moonshot
* 2023-12-11 (ee3984a3): Merged PR 541: fixed the issue in getFileUpdatedDate func
* 2023-12-11 (bad356f9): fixed the issue in getFileUpdatedDate func
* 2023-12-11 (c55a4bc1): Merged PR 540: made it mobile responsive
* 2023-12-11 (02549021): made it mobile responsive
* 2023-12-08 (8acc0458): Merged PR 189: Revert 'Deploy'
* 2023-12-08 (bee226c0): Revert "Merged PR 188: Deploy"
* 2023-12-08 (3f67e77a): Merged PR 188: Deploy
* 2023-12-08 (e611713e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-08 (5c23c489): Merged PR 538: integration changes for cum avg be changes
* 2023-12-08 (d3f6f35d): integration changes for cum avg be changes
* 2023-12-08 (1223f75d): Merged PR 537: added the missed AZURE\_STORAGE\_RAW\_BLOB
* 2023-12-08 (5a8c5b88): added the missed AZURE\_STORAGE\_RAW\_BLOB
* 2023-12-08 (b2c669c8): Merged PR 536: Generate the monthly cumulative average data updated date
* 2023-12-08 (cbcab35b): reverted efficiency cum chart changes
* 2023-12-08 (c623f883): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-214-BE-changes
* 2023-12-08 (181fee3e): Generate the monthly cumulative average data updated date
* 2023-12-08 (15d68dd3): Merged PR 534: New Scoring for Home Page Score Cards changes
* 2023-12-08 (c8796b83): New Scoring for Home Page Score Cards changes
* 2023-12-07 (f4c8c5b5): Merged PR 187: Deploy
* 2023-12-07 (ce48a549): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-07 (839464b8): Merged PR 533: changed the zoom levels of maps
* 2023-12-07 (903745a1): changed the zoom levels of maps
* 2023-12-07 (76518b54): Merged PR 186: Deploy
* 2023-12-07 (426d2762): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-07 (49f6833d): Merged PR 531: Fixed repetitive map issue
* 2023-12-07 (c81cc23c): Fixed repetitive map issue
* 2023-12-07 (de8175c1): Merged PR 185: Deploy
* 2023-12-07 (6762f630): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-07 (d4acf696): Merged PR 529: added transition for view full indicator button
* 2023-12-07 (a123b689): added transition for view full indicator button
* 2023-12-07 (d8213151): Merged PR 527: FIxed the issue in isOnTrack text changes in home page cards
* 2023-12-07 (00b63b29): FIxed the issue in isOnTrack text changes in home page cards
* 2023-12-07 (30b7101b): Merged PR 525: New Scoring for Home Page Score Cards
* 2023-12-07 (2cfe29f2): New Scoring for Home Page Score Cards
* 2023-12-07 (3f5da5f7): Merged PR 522: View full indicator hover changes
* 2023-12-07 (f3b6712c): fixed merge conflicts
* 2023-12-07 (97f9dd6a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-229-ui
* 2023-12-07 (e4c8e323): view full indicator hover changes
* 2023-12-07 (039144a2): Merged PR 520: fixed issues in comments on ifd card and note card
* 2023-12-07 (b1e84349): Merged PR 519: home page stat card hover changes
* 2023-12-07 (ee64ae53): fixed issues in comments on ifd card and note card
* 2023-12-06 (1c2341ea): home page stat card hover changes
* 2023-12-06 (d416447e): Merged PR 184: Indicator score
* 2023-12-06 (2c446406): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-06 (d919db22): Merged PR 517: VALUES\_TREND\_LINE\_DATA indicator score added
* 2023-12-06 (7f9a34fc): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-229-ui
* 2023-12-06 (dd274a5a): VALUES\_TREND\_LINE\_DATA indicator score added
* 2023-12-06 (2e7dcf98): view indicator button changes
* 2023-12-06 (341a7bb8): Merged PR 183: Deploy
* 2023-12-06 (4c2558e9): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-06 (3f90323c): Merged PR 515: navigate sections done
* 2023-12-06 (b5bbdce3): resolved merge conflict
* 2023-12-06 (cb58f918): updated and removed unncessary code
* 2023-12-06 (d782e24c): navigate to pages and sections on card click
* 2023-12-05 (0a79d87f): Merged PR 182: Deploy
* 2023-12-05 (2bca1902): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-05 (bd9f2ee2): Merged PR 514: clear nav cache
* 2023-12-05 (e7ed4dd5): clear nav cache
* 2023-12-05 (0fb06547): Merged PR 181: Deploy
* 2023-12-05 (f23313b6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-05 (37e48341): Merged PR 512: people page text changes
* 2023-12-05 (547a0064): people page text changes
* 2023-12-05 (6eb22401): Merged PR 180: Deploy
* 2023-12-05 (339c1545): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-05 (5a3544ff): Merged PR 508: Add induvidual score for moonshot
* 2023-12-05 (14cb6b71): Merged PR 510: Removed Icon from Individual Indicator Cards
* 2023-12-05 (58b1c350): Merged PR 507: changed text 'Contributions' -> 'Resources Mobilization'
* 2023-12-05 (05f811c1): Merged PR 509: Cumulative Average Month-by-Month Trendline with September 2023 Highlight dyn...
* 2023-12-05 (80069bc6): Update names
* 2023-12-05 (616ad712): Add method to get the file update date.
* 2023-12-05 (8794ee7d): Removed Icon from Individual Indicator Cards
* 2023-12-05 (70bb37e7): Cumulative Average Month-by-Month Trendline with September 2023 Highlight dynamic text changes and added linear interpolation func to calculate the middle values
* 2023-12-05 (8431d3c5): Add induvidual score for moonshot
* 2023-12-05 (69283aff): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-12-05 (a08e5ae7): addition of indicator score calculation
* 2023-12-05 (629f427f): added navigateTo mainStatCard
* 2023-12-05 (b6721ca9): changed text 'Contributions' -> 'Resources Mobilization'
* 2023-12-05 (c67ec62a): Merged PR 505: Removed rounded borders and revert the bar thickness to original values
* 2023-12-05 (3b91bc7a): removed rounded borders and revert the bar thickness to default
* 2023-12-05 (b4071ba4): removed rounded borders and revert the bar thickness to default
* 2023-12-04 (8f2ff8b3): Merged PR 179: Deploy
* 2023-12-04 (58bea5c8): Merged PR 178: Deploy
* 2023-12-04 (f377ab15): Merged PR 504: fixed issue in graph largest score decrease chart
* 2023-12-04 (d9d37e94): updated
* 2023-12-04 (62c93b64): fixed issue in cards reverted
* 2023-12-04 (037fd5c4): Merged PR 503: Accountability page text changes
* 2023-12-04 (ca0b0e65): accountability page changes
* 2023-12-04 (0ad15598): Merged PR 502: resolve acoountability and ifd issues
* 2023-12-04 (f3413182): resolve acoountability and ifd issues
* 2023-12-04 (a27379ab): fixing round corners when drawing is inverted
* 2023-12-04 (8fab147a): Merged PR 501: Updated env
* 2023-12-04 (22fe61c3): accountability page text changes
* 2023-12-04 (c67b99e7): Updated env
* 2023-12-04 (0379d1dc): Merged PR 499: Home page text changes
* 2023-12-04 (0af5e4ae): Merged PR 500: impact page text changes
* 2023-12-04 (461eb343): impact page text changes
* 2023-12-04 (e99e2d2f): Home page text changes
* 2023-12-04 (59ee3593): Merged PR 497: dynamically deciding the borders to round and not to round
* 2023-12-04 (232f9503): updated
* 2023-12-04 (7290e97d): dynamically deciding the borders to round and not to round
* 2023-12-01 (e8444522): Merged PR 177: Sync
* 2023-12-01 (cd464bf2): Merged PR 176: Sync
* 2023-12-01 (bb8b2bde): Merge branch 'develop' into pr67
* 2023-12-01 (4851b981): Merged PR 495: home page UI figma design changes
* 2023-12-01 (8d8f9f27): home page UI figma design changes
* 2023-12-01 (6a907c6c): Merged PR 493: made signature solutions thinner
* 2023-12-01 (0f4a2686): Merged PR 492: resolve merge conflicts
* 2023-12-01 (03e35421): made signature solutions thinner
* 2023-12-01 (e380af63): resolve merge conflicts
* 2023-12-01 (c37fd573): Merged PR 490: bargraph border round feature
* 2023-12-01 (4818a283): fixed the rounded issue in stacked bar graphs and made the bars thin
* 2023-12-01 (393a915a): Merged PR 488: Guage component changes for indicator scores
* 2023-12-01 (a2926b49): efficiency page indicator score changes
* 2023-12-01 (dd721eee): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-208-ui
* 2023-12-01 (78390166): Guage component changes for indicator scores
* 2023-12-01 (d5ae6aa5): Merged PR 487: Test trigger
* 2023-12-01 (fbffaac5): Merge branch 'develop' into function\_improvment
* 2023-12-01 (03f39e0a): Change env files
* 2023-12-01 (d2c42c45): Merged PR 486: Revert 'Add endoint to update files'
* 2023-12-01 (1db5571b): Revert "Merged PR 485: Add endoint to update files
* 2023-12-01 (77fcf783): Merged PR 485: Add endoint to update files
* 2023-12-01 (d1d38b8e): Add endoint to update files

### November

* 2023-11-30 (e830c48b): Merged PR 175: Deploy
* 2023-11-30 (19dedd10): Merged PR 174: Dev changes
* 2023-11-30 (e5d712b7): Merged PR 484: remove caching
* 2023-11-30 (43009e35): remove caching
* 2023-11-30 (57342da8): Merged PR 482: Cumulative Average Month-by-Month Trendline with September 2023 Highlight sta...
* 2023-11-30 (1dcd662b): undp delivery analysis cumulative avg stat changes
* 2023-11-30 (8fcce2ec): Cumulative Average Month-by-Month Trendline with September 2023 Highlight stat logic changes
* 2023-11-30 (2ce36612): Merged PR 481: hide just for you section
* 2023-11-30 (9594603e): hide just for you section
* 2023-11-30 (9833f1c9): Merged PR 479: showing contribution score coming from BE in the frontend
* 2023-11-30 (f8292654): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into make-bargraph-borders-round
* 2023-11-30 (8da54b71): showing contribution score coming from BE in the frontend
* 2023-11-30 (9a3cfcac): Merged PR 474: off track, on track text change
* 2023-11-30 (27bf7b8f): updated stat cards to hide unnecessary empty card dynamically according to screen width, fix issues in for you section
* 2023-11-30 (f77f7548): improved card design and fixed issues
* 2023-11-30 (1c0bcbdd): Merged PR 477: global stat card changes
* 2023-11-30 (f00997cd): home page report cards content changes
* 2023-11-30 (e4051a65): global stat card changes
* 2023-11-30 (c7d6ab8f): made updates
* 2023-11-30 (f8d10037): resolved merged conflict
* 2023-11-30 (f7006e59): Merged PR 475: Latest changes
* 2023-11-29 (122d6a71): Merged PR 173: Deploy
* 2023-11-29 (2458e357): Merged PR 172: Deploy
* 2023-11-29 (012b1daf): Update text changes
* 2023-11-29 (c12f4494): Text changes
* 2023-11-29 (ac299043): off track, on track text change
* 2023-11-29 (d97512f7): Merged PR 171: Deploy
* 2023-11-29 (6e7d79b1): Merged PR 170: Update text
* 2023-11-29 (476bc1ef): Update text
* 2023-11-29 (d11b8452): Merged PR 169: Latest
* 2023-11-29 (e1b8d6de): Merged PR 168: Off track fix
* 2023-11-29 (f5000cdc): Off track fix
* 2023-11-29 (499e9cb0): Merged PR 473: Styling issues
* 2023-11-29 (f3f11680): Merged PR 167: Deploy
* 2023-11-29 (5f583a4c): Merged PR 166: Remove ticks
* 2023-11-29 (58e707b1): Remove ticks
* 2023-11-29 (a7f80749): Merged PR 165: Deploy
* 2023-11-29 (80385e78): Merged PR 164: Sync
* 2023-11-29 (9e572a6a): update styles
* 2023-11-29 (8f971a41): improvements
* 2023-11-29 (4e9a5eac): Merged PR 163: Deploy
* 2023-11-29 (2bdba9e3): Merged PR 162: Deploy
* 2023-11-29 (5e340246): update report card styles
* 2023-11-29 (74d8f3eb): Merged PR 472: update stat cards
* 2023-11-29 (4d85572e): stat cards
* 2023-11-29 (b58f2411): resolved merge conflict
* 2023-11-29 (bbda8b42): basic stat cards done
* 2023-11-29 (bc0bd19a): Update report margin bottom
* 2023-11-29 (a403983b): Add navigation
* 2023-11-29 (5b5b7b12): Merged PR 470: report card changes
* 2023-11-29 (95d12d73): report card changes
* 2023-11-29 (804a6469): Merged PR 468: created gauge chart
* 2023-11-29 (675e0675): Merged PR 467: Add ifd induvidual score
* 2023-11-29 (a3a6f79a): created gauge chart
* 2023-11-29 (8a1bdb12): Add ifd induvidual score
* 2023-11-29 (1616b611): Update IFD
* 2023-11-29 (35a87238): Merged PR 466: legend styles changes
* 2023-11-29 (9a6de9eb): legend styles changes
* 2023-11-29 (b9d443fc): updated
* 2023-11-29 (b02c5c05): updated
* 2023-11-28 (97bee963): Merged PR 161: Deploy
* 2023-11-28 (596ce708): Merged PR 160: Sync
* 2023-11-28 (eeeb1dcc): Merged PR 464: card component refactoring changes
* 2023-11-28 (9cd3d7aa): Deleted unwanted files
* 2023-11-28 (5f7ae0ff): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-component-changes
* 2023-11-28 (54e0fcca): card component refactoring changes
* 2023-11-28 (de1e763d): made the corners of bar graphs round
* 2023-11-28 (94314422): Update azure-pipelines.yml for Azure Pipelines
* 2023-11-28 (54653d3e): Merged PR 462: Update files
* 2023-11-28 (fb9a77b3): Update files
* 2023-11-28 (4b7e5492): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-11-28 (2d4a9cac): merged dev
* 2023-11-28 (78635136): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-component-changes
* 2023-11-28 (305669c8): Merged PR 461: change variables
* 2023-11-28 (b3373194): update dashboard.ts
* 2023-11-27 (b39f96db): Data card component updates and mapbox styles and token updates
* 2023-11-27 (3d7e2190): Merge branch 'develop' into staging
* 2023-11-27 (a9234ea9): Merged PR 158: Deploy
* 2023-11-27 (0d05b7ab): Merge branch 'develop' into pr63
* 2023-11-27 (db323b33): Merged PR 459: updated icons
* 2023-11-27 (a790ca27): updated
* 2023-11-27 (8aff7da6): update names
* 2023-11-27 (8a204af6): Update azure-pipelines.yml for Azure Pipelines
* 2023-11-27 (2bc08d76): Update azure-pipelines.yml for Azure Pipelines
* 2023-11-27 (29b568d4): Merged PR 458: Merge datacube-triger to develop
* 2023-11-27 (9d9901c8): Set up CI with Azure Pipelines
* 2023-11-27 (49fb340c): update files
* 2023-11-27 (8cd784d4): Merge branch 'fixes' into fusion-data-azure
* 2023-11-27 (6d8b83f4): Complete ifd
* 2023-11-27 (317611ab): Merged PR 456: created new stat cards component
* 2023-11-27 (194ffe8f): fixed some ui issues
* 2023-11-27 (5b360055): created new stat cards
* 2023-11-27 (3c09078a): update connection string
* 2023-11-27 (247a77a1): Update trigger.cs
* 2023-11-27 (9e914739): update data fusion
* 2023-11-27 (9e1866a8): Change audit mapper
* 2023-11-27 (8d55a5b4): added icons for new stat cards
* 2023-11-24 (61631daa): Merged PR 157: Deploy
* 2023-11-24 (a4558ffc): Merged PR 156: Sync
* 2023-11-24 (5d06c698): Merged PR 455: fixed issue in overview not getting highlight on '/'
* 2023-11-24 (58ba0afb): fixed issue in overview not getting highlight on '/'
* 2023-11-24 (5fa2afb7): Merged PR 155: Deploy
* 2023-11-24 (c70b9a18): Merged PR 154: Sync
* 2023-11-24 (b9f4176c): Updated homeMapper.ts
* 2023-11-24 (35cf371c): Completed without IFD
* 2023-11-24 (22dea4b7): Merged PR 453: created breadcrumbs using tailwindcss and updated
* 2023-11-24 (5bd039f9): fixed issue in getting shaked on page change
* 2023-11-24 (4bd4791d): updated
* 2023-11-24 (95841374): made the header tabs scrollable
* 2023-11-24 (b76b397b): Merged PR 153: Revert "Updated config.ts"
* 2023-11-24 (47f54415): Revert "Updated config.ts"
* 2023-11-24 (8e64fa7e): Update azure-pipelines\_filecopy.yml for Azure Pipelines
* 2023-11-24 (2c1c738f): Update azure-pipelines\_filecopy.yml for Azure Pipelines
* 2023-11-24 (a1cbad6b): Update azure-pipelines\_filecopy.yml for Azure Pipelines
* 2023-11-24 (ac6c724d): Update azure-pipelines\_filecopy.yml for Azure Pipelines
* 2023-11-24 (04bfcfe3): removed unnecessary code
* 2023-11-24 (42bf3f4c): fixed issue in missing prop
* 2023-11-24 (c6d37d01): created IHeader file
* 2023-11-24 (d0b4546a): created own INavLink, INavLinkGroup and IBreadcrumbItem
* 2023-11-24 (56cbdac3): updated links in impact page
* 2023-11-24 (6920c071): fix issue in footer logo getting cut off on loading
* 2023-11-24 (0b4e6d5f): updated margins of breadcrumbs component
* 2023-11-24 (71ee7ef2): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-24 (aab8719b): Updated config.ts
* 2023-11-24 (cad74372): created new breadcrumbs component and updated the navigation links
* 2023-11-24 (f0b6d694): Completed contributions
* 2023-11-23 (2519beea): Merged PR 152: Deploy
* 2023-11-23 (6dce4d4c): Merged PR 151: Deploy
* 2023-11-23 (4c053f20): function updated
* 2023-11-23 (e73f9a9b): Merged PR 451: new header with tailwind css
* 2023-11-23 (5004a6be): updated styles
* 2023-11-23 (e5237f01): fixed UI issues in focus cards and changed bg-color
* 2023-11-23 (072650a7): increased the right padding in table
* 2023-11-23 (86f78ffa): increased gap between tabs in header
* 2023-11-23 (3bb125d6): updated header with tailwind css
* 2023-11-23 (e788a8b1): Update Program.cs
* 2023-11-23 (dbf15557): Add azure function
* 2023-11-23 (9260c20c): Merged PR 449: updated to import tailwind from assets in the src
* 2023-11-23 (d1ef97b9): updated to import tailwind from assets in the src
* 2023-11-23 (88c01e2e): Update program.cs
* 2023-11-23 (bc3e7728): Remove test cases
* 2023-11-23 (7e2cb223): Merged PR 448: Add datacube
* 2023-11-23 (b85c2c7a): delete obj folder
* 2023-11-23 (87f0a0b4): Update delivery file
* 2023-11-23 (e90e7a69): Merged PR 446: updated gulpfile and import for tailwind.css
* 2023-11-23 (2f074437): updated gulpfile and import for tailwind.css
* 2023-11-23 (3e7eaf1f): Update logic
* 2023-11-23 (ed77879b): Updated structure
* 2023-11-23 (a0996c49): Merged PR 442: moved away from detailList and used tailwind to create tables
* 2023-11-23 (a50486a3): Update method name
* 2023-11-23 (bb8b6d57): Add azure file upload functionlity
* 2023-11-23 (1a80705c): Update querries
* 2023-11-23 (7db677e5): Update the directory
* 2023-11-22 (ed1b2d1e): Merged PR 443: Files updated
* 2023-11-22 (53a2371f): Files updated
* 2023-11-22 (a08924e8): Update program.cs
* 2023-11-22 (fec5b371): Updated config.ts
* 2023-11-22 (3dc7f374): Change connection string
* 2023-11-22 (2fd6be1d): moved from fluent UI detailList to table built with table
* 2023-11-22 (a5710d8a): added font inter
* 2023-11-22 (5ae872e5): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-22 (2c88d46a): Merged PR 148: Deploy
* 2023-11-22 (840e7b07): Merged PR 147: Deploy
* 2023-11-22 (358802e1): added headlessUI and heroicons
* 2023-11-22 (de2eaff0): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-22 (fd475d35): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-22 (7b6fa1ba): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-22 (c7aac8e6): Merged PR 441: Update pipeline
* 2023-11-22 (8f20f1c6): Update connection string
* 2023-11-22 (934e756f): Update pipeline
* 2023-11-22 (f278641e): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-11-22 (61c2eb99): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-11-22 (d8758246): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-11-22 (30dc2d34): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-11-22 (4863a570): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-11-22 (0560598b): Merged PR 440: update dev
* 2023-11-22 (5fc96771): update dev
* 2023-11-22 (b849ca5c): Merged PR 146: Revert "Revert "Change configs"
* 2023-11-22 (b45807e1): Revert "Revert "Change configs"
* 2023-11-22 (a4487670): Revert "Change configs"
* 2023-11-22 (880d74fd): Change configs
* 2023-11-22 (85a76113): Merged PR 439: Update yml file
* 2023-11-22 (d8ed1a48): Update yml file
* 2023-11-22 (bea34bd3): Update program.cs
* 2023-11-22 (5f97852f): Merged PR 438: Commented test cases
* 2023-11-22 (8183af18): Updated commented lines
* 2023-11-22 (9f0731eb): Commented test cases
* 2023-11-22 (9d5f1ca1): delete files
* 2023-11-22 (3379cdc5): fixed issue in header texts overflowing
* 2023-11-22 (6320380c): updated content paths and added base styles
* 2023-11-22 (f514aeef): Merged PR 437: change test script
* 2023-11-22 (7d462774): change test script
* 2023-11-22 (9421fa5c): Update files
* 2023-11-21 (0b47c647): Merged PR 145: Deploy
* 2023-11-21 (a50eed05): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-21 (db746384): Merged PR 144: Deploy
* 2023-11-21 (ec9031f1): Merged PR 435: Update files
* 2023-11-21 (694a7608): Update files
* 2023-11-21 (cfd0ccd9): Update data
* 2023-11-21 (1a830445): Merged PR 434: Restructure response array
* 2023-11-21 (145c899c): Restructure response array
* 2023-11-21 (e183aad5): Update files
* 2023-11-21 (9b70bff9): Merged PR 142: Sync
* 2023-11-21 (033de8f9): Merged PR 140: Files
* 2023-11-21 (b2d48646): Merged PR 432: Update files
* 2023-11-21 (5ec59bb6): Update files
* 2023-11-21 (eefd9450): Complete delivery and institutional files
* 2023-11-21 (1212f168): Updated programe.cs
* 2023-11-21 (73274b93): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-11-21 (ea404ddf): rechecking and changes made to values, ifd and coc+inform matrix
* 2023-11-21 (ab5850bb): Merged PR 430: integrate tailwind css and removed warning that arosed due to autoprefixer
* 2023-11-21 (dc93b143): changed start to flex-start to remove autoprefixer warning
* 2023-11-21 (cadb453e): added tailwind css
* 2023-11-20 (e7317c2f): Merged PR 428: Refactor Indicators
* 2023-11-20 (d9d1a0f2): Refactored the code
* 2023-11-20 (d5d94c21): Update connection string
* 2023-11-20 (d3882f3f): remove the csv file
* 2023-11-20 (1a3cf6b4): Complete home mapper
* 2023-11-17 (2ef024e2): data-cube querying completed
* 2023-11-17 (5cc22693): refactored
* 2023-11-17 (6643746c): Added new queries
* 2023-11-17 (f681b5ea): Restructure Program.cs file
* 2023-11-16 (033e6e16): Add data cube app
* 2023-11-15 (073e3d7d): Remove console logs
* 2023-11-15 (4e1d24fe): Complete accountability page
* 2023-11-14 (b21ce8b6): Resolve lint and test issues
* 2023-11-13 (f9e80bed): Revert "Revert "complete impact page""
* 2023-11-13 (940c129e): Revert "complete impact page"
* 2023-11-13 (bae09fcd): Merge branch 'develop' into PERF-195
* 2023-11-13 (d3bd4797): complete impact page
* 2023-11-10 (1f2e1040): Refactor peoples page
* 2023-11-10 (5f62b55d): Merged PR 429: Changed targetmet logic
* 2023-11-10 (6ca6e5f5): Changed targetmet logic
* 2023-11-10 (0200efa5): Resolve year issue
* 2023-11-10 (d7826146): remove console logs
* 2023-11-10 (26a1f6cf): Merge branch 'develop' into PERF-195
* 2023-11-10 (d80e73b7): Revamp value page
* 2023-11-09 (f7818d3f): Merged PR 139: Deploy
* 2023-11-09 (3a97a853): Merged PR 138: Deploy
* 2023-11-09 (39241d59): Merged PR 426: added Countries Performance in Meeting Emission Targets in greening section
* 2023-11-09 (35d1d528): Merged PR 425: Resolve irrf heatmap issue
* 2023-11-09 (9bacdd05): added Countries Performance in Meeting Emission Targets in greening section
* 2023-11-08 (25bf6a98): Merged PR 424: changes in VALUES\_TARGET\_ACHIEVED\_COUNTRIES stat
* 2023-11-08 (9b632a4c): changes in VALUES\_TARGET\_ACHIEVED\_COUNTRIES stat
* 2023-11-08 (031b0247): Merge branch 'develop' into Improve/generality
* 2023-11-08 (d5c62f7e): Resolve irrf heatmap issue
* 2023-11-08 (25402069): fixed an issue in Distribution of Total IFD Scores
* 2023-11-08 (cfee9fba): adding indicator test scripts
* 2023-11-07 (665798f8): Merged PR 423: lint issue fixes
* 2023-11-07 (880a71f0): lint issue fixes
* 2023-11-07 (97e37355): Merged PR 422: fixed lint issues
* 2023-11-07 (7b85a501): fixed lint issues
* 2023-11-07 (0f64e0c9): Merged PR 421: Test cases fixes
* 2023-11-07 (189d90e1): annualGHG changes
* 2023-11-07 (1d8090aa): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-195-be
* 2023-11-07 (1100649d): test cases update
* 2023-11-07 (f8064c3f): Merged PR 418: Resolve the bin issue
* 2023-11-07 (16230a42): Merged PR 419: Countries Performance in Meeting Emission Targets BE changes
* 2023-11-07 (42b48a22): updated test cases for VALUES\_TARGET\_ACHIEVED\_COUNTRIES
* 2023-11-07 (b73b9b40): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-195-be
* 2023-11-07 (935461df): Countries Performance in Meeting Emission Targets BE changes
* 2023-11-07 (9cdcec74): Resolve the bin issue
* 2023-11-07 (9783bd5f): Merged PR 417: Changed the rounding method
* 2023-11-07 (a3ae6807): Changed the rounding method
* 2023-11-06 (ba865fda): Merged PR 416: Heatmap revamp
* 2023-11-06 (c5176d3f): Merge branch 'develop' into PERF-197
* 2023-11-06 (dec553e4): Corrected heatmap values
* 2023-11-03 (176b7f10): Merged PR 415: fixed the issue in getCleaned value function
* 2023-11-03 (0cb47e45): fixed the issue in getCleaned value function
* 2023-11-03 (df5e9290): Merged PR 414: fixed lint issue
* 2023-11-03 (86cb6d46): fixed lint issue
* 2023-11-03 (79a17ed9): Merged PR 413: Fixed the mismatched logic behind Percentage of Targets Met for Each Month of...
* 2023-11-02 (cac2146f): Fixed the mismatched logic behind Percentage of Targets Met for Each Month of Each Year
* 2023-11-02 (3f74a82d): Merged PR 412: Total Emissions by Year with Trend Line (tCO2e) filter fixes
* 2023-11-02 (eda59794): Total Emissions by Year with Trend Line (tCO2e) filter fixes
* 2023-11-02 (5a2f547a): Merged PR 411: Resolve value issues
* 2023-11-02 (ba49a233): Update test cases
* 2023-11-02 (e9a20fc6): Resolve values issue
* 2023-11-01 (c9486a28): Updated coRatingHandler.ts
* 2023-11-01 (4f6e3e39): Updated homeMapper.ts
* 2023-11-01 (49151287): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-01 (8a88ba59): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-11-01 (23afaa25): Merged PR 137: Revert 'Revert 'Deploy''
* 2023-11-01 (fe27c824): Revert "Revert "Merged PR 132: Deploy""
* 2023-11-01 (05a916e2): Revert "Merged PR 134: Revert 'Deploy'

### October

* 2023-10-31 (def8e702): Merged PR 134: Revert 'Deploy'
* 2023-10-31 (585c84e5): Revert "Merged PR 132: Deploy"
* 2023-10-31 (a068a76c): Merged PR 132: Deploy
* 2023-10-31 (7473c290): Merged PR 131: Latest
* 2023-10-31 (50513999): Merge branch 'develop' into pr50
* 2023-10-31 (e44d827e): Merged PR 409: Resolve naming issues
* 2023-10-31 (fb714bb2): Resolve naming issues
* 2023-10-31 (45607cd0): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-10-31 (0ddecefb): Merged PR 408: undp delivery analysis handler fix
* 2023-10-31 (7a899495): undp delivery analysis handler fix
* 2023-10-31 (87281eda): Merged PR 407: Accountability page dynamic text changes
* 2023-10-31 (c9cf5f52): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-10-31 (b6dcdcf7): people section dynamic text changes
* 2023-10-31 (5563311c): people section dynamic text changes
* 2023-10-31 (991f5f25): accountability page dunamic text changes
* 2023-10-31 (318b8dc2): Merged PR 406: merge files into dev
* 2023-10-31 (09cefbda): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-10-31 (4961b24f): Accountability page dynamic text changes
* 2023-10-30 (f6f9f48b): add log
* 2023-10-30 (ad77e7b7): change file name
* 2023-10-30 (25814665): Updated coRatingHandler.ts
* 2023-10-30 (ec17ea8a): Updated homeMapper.ts
* 2023-10-30 (f51bfb92): Updated coRatingHandler.ts
* 2023-10-30 (f1cca47e): Merged PR 130: st
* 2023-10-30 (32ba6309): Merged PR 129: Update filename
* 2023-10-30 (13f129de): Update filename
* 2023-10-30 (e28dc868): Merged PR 405: Rename the sheet
* 2023-10-30 (c7bc6064): Merged PR 127: Change file sheet name
* 2023-10-30 (8e5ec323): Rename the sheet
* 2023-10-30 (563bb9e0): Change file sheet name
* 2023-10-30 (a45d378f): Update azure-pipelines\_filecopy.yml for Azure Pipelines
* 2023-10-30 (c1dde150): Merged PR 404: add new file
* 2023-10-30 (797212be): add new file
* 2023-10-30 (5aab2f65): Merged PR 125: Add new file
* 2023-10-30 (b555be91): Add new file
* 2023-10-30 (fb1ae7ba): Merged PR 403: Test
* 2023-10-30 (a6b529d1): Update file
* 2023-10-30 (1572b737): Merged PR 123: Update data
* 2023-10-30 (6cfa0bf0): Update file
* 2023-10-30 (ad314874): Merge branch 'develop' into pr49
* 2023-10-30 (9ca1d241): Update data
* 2023-10-30 (e32dd189): Merged PR 402: Change the header of the file
* 2023-10-30 (1e3fa817): Change the header of the file
* 2023-10-30 (854020c4): Change the file
* 2023-10-30 (f51e571c): Merged PR 401: AUDIT\_LATEST\_RATING BE changes
* 2023-10-30 (d6e30779): Merged PR 399: Add filters to trendline
* 2023-10-30 (fd143e8e): Merged PR 400: merge dev into files
* 2023-10-30 (a4b7a856): AUDIT\_LATEST\_RATING BE changes
* 2023-10-30 (c64513f8): Merge branch 'develop' into Refactoring/Mappers
* 2023-10-30 (1cc558af): Merge branch 'develop' into Refactoring/Mappers
* 2023-10-30 (bc459fe8): Add country filter to trendline
* 2023-10-30 (d8e0295d): Merged PR 398: filter changes in greening section
* 2023-10-30 (254eb886): filter changes in greening section
* 2023-10-27 (f68b093b): Merged PR 121: Deploy
* 2023-10-27 (1eebc82b): Merged PR 120: Latest issues
* 2023-10-27 (734b7881): Merged PR 395: \[Inprogress] Update filter values
* 2023-10-27 (1547719b): Merged PR 397: fixes in totalContribution handler
* 2023-10-27 (9eaa0e11): fixes in totalContribution handler
* 2023-10-27 (57fadd8c): Merged PR 118: Deploy
* 2023-10-27 (9a830de9): Merged PR 117: Data updates
* 2023-10-27 (0d47ec7b): Merge branch 'develop' into pr48
* 2023-10-27 (0884477b): Merge branch 'develop' into pr48
* 2023-10-27 (067582af): Merged PR 396: Dynamic Description Text for Current Vacancy Rate by Bureau
* 2023-10-27 (153eef88): Update filter values
* 2023-10-27 (885eafac): Merged PR 394: merge dev into files
* 2023-10-27 (c9d112ff): Merged PR 393: Refactor inforam & CO file
* 2023-10-27 (67bb6f59): Update files
* 2023-10-27 (b7783d75): Merge branch 'develop' into Refactoring/Mappers
* 2023-10-27 (044f91a6): Refactor inforam & CO file
* 2023-10-27 (8f2a6200): Dynamic Description Text for Current Vacancy Rate by Bureau
* 2023-10-26 (749b6b91): Merged PR 391: PEOPLE\_VACANCY\_RATE backend changes for totalEncumberedPost, totalVacantPosts and vacancyRateAvg
* 2023-10-26 (378fe7d5): irrf\_indicator changes
* 2023-10-26 (182e7244): Merged PR 116: Deploy
* 2023-10-26 (1cf98816): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-189-fe
* 2023-10-26 (513b8e04): Merged PR 115: add perc
* 2023-10-26 (b920abad): add perc
* 2023-10-26 (58b16834): added percentage for irrf desc impactPage
* 2023-10-26 (2fd1c0f5): PEOPLE\_VACANCY\_RATE backend changes for totalEncumberedPost, totalVacantPosts and vacancyRateAvg
* 2023-10-26 (c84391e2): Merged PR 114: Deploy
* 2023-10-26 (bce3a502): Merged PR 113: IRRF
* 2023-10-26 (4dba47ba): Merged PR 389: Resolve IRRF issue
* 2023-10-26 (a634f12e): Merged PR 388: Impact page changes
* 2023-10-26 (4cbbb82e): Resolve IRRF issue
* 2023-10-26 (a04caba6): impact page changes
* 2023-10-26 (bfd265fa): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-186-fe
* 2023-10-26 (def1b502): impact page changes
* 2023-10-26 (e91342c2): impact page changes
* 2023-10-25 (7b1c983a): Merged PR 112: Deploy
* 2023-10-25 (cd97f75a): Merged PR 111: Deploy
* 2023-10-25 (622aebe6): hard code value
* 2023-10-25 (1acfb82e): Merged PR 387: resolve IRRF issue
* 2023-10-25 (27ec9e19): resolve IRRF issue
* 2023-10-25 (60bb079a): Merged PR 110: Deploy
* 2023-10-25 (12cdf06f): Merged PR 109: Deploy
* 2023-10-25 (cb88e9cf): Merged PR 386: Change global score
* 2023-10-25 (c4aac11d): Change global score
* 2023-10-25 (bf49ab0e): Merged PR 107: Deploy
* 2023-10-25 (d0a75653): Merged PR 106: IRRF
* 2023-10-25 (bea12d9e): Merged PR 385: merge develop into files
* 2023-10-25 (36e70490): Merged PR 384: Resolve IRRF issues
* 2023-10-25 (e1944676): resolve lint isusues
* 2023-10-25 (67e2b113): Add irrf
* 2023-10-25 (2ca6f15f): Merged PR 383: Updated IRRF Scoring based on new methodology
* 2023-10-25 (82e891a7): Updated IRRF Scoring based on new methodology
* 2023-10-25 (2749cd79): Merged PR 382: EfficeincyMapper changes
* 2023-10-25 (afc6de80): efficiencyMapper changes
* 2023-10-25 (02d56e31): efficiencyMapper changes
* 2023-10-24 (6f82f1f9): resolve lint issues
* 2023-10-24 (ebd6eacb): Commented test cases
* 2023-10-24 (43d17b49): Updated azure-pipelines-server.yml
* 2023-10-24 (6474630d): Merged PR 104: Deploy
* 2023-10-24 (369dd06f): Merged PR 103: IRRF
* 2023-10-24 (5e0c7d34): Merged PR 379: Removed the indicators which has zero for a selected set of columns
* 2023-10-24 (66e8d3b0): Update irrf mapper
* 2023-10-24 (a9b1765c): removed the indicators which has zero for a selected set of columns
* 2023-10-24 (3c1d3120): Merged PR 378: Improved efficiency mapper
* 2023-10-24 (3455f283): operation file changes
* 2023-10-24 (8ea78838): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-refactor-mapper-changes
* 2023-10-24 (c2ad3c54): imporve efficiency mapper
* 2023-10-24 (a3ce21f3): Merged PR 377: Update in desc and legends on COA
* 2023-10-24 (026c8dc3): Update in desc and legends on COA
* 2023-10-24 (9981778e): Description changes in Accountability page 5 Unsatisfactory Audits card
* 2023-10-24 (f7b585c0): Merged PR 376: Improve audit mapper
* 2023-10-24 (b57db018): Improve audit mapper
* 2023-10-24 (06a5cdf5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-refactor-mapper-changes
* 2023-10-24 (3bd1dfa2): Merged PR 375: impact page Average ICPE Rating Score for 2022 description changes
* 2023-10-24 (f2c13c1f): impact page Average ICPE Rating Score for 2022 description changes
* 2023-10-24 (9ec7624d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-refactor-mapper-changes
* 2023-10-23 (fb30e399): delivery\_data.ts file changes
* 2023-10-23 (52655caf): Merged PR 102: Deploy
* 2023-10-23 (3aa8cf1f): Merged PR 101: IRRF description fix
* 2023-10-23 (2d49748b): Merge branch 'develop' into pr42
* 2023-10-23 (25282136): changes in delivery\_data.ts file
* 2023-10-23 (c4644c34): Merged PR 372: Refactor irrfMappers
* 2023-10-23 (63f40b6a): efficiency mapper refactoring changes
* 2023-10-23 (667c7aa6): remove spaces
* 2023-10-23 (4035ad6c): Remove unwanted lines
* 2023-10-23 (96ccb756): Improve column name usage
* 2023-10-23 (853b3efc): Merged PR 373: Update CO Performance in Meeting IRRF Milestones Description
* 2023-10-23 (dbed5677): Add irrf indicator score
* 2023-10-23 (e6abb84d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-refactor-mapper-changes
* 2023-10-23 (49b97e11): Update CO Performance in Meeting IRRF Milestones Description
* 2023-10-23 (285515ed): refactoring changes in efficiency mapper
* 2023-10-20 (eda045da): Merged PR 100: Deploy
* 2023-10-20 (1fa47e37): Merged PR 99: Change desc
* 2023-10-20 (b1af36ba): Change desc
* 2023-10-20 (d9a278d8): Refactor irrfMappers
* 2023-10-20 (d3e9bfee): Merged PR 97: Deploy
* 2023-10-20 (394cf0c7): Merged PR 96: IRRF Changes
* 2023-10-20 (28895736): Merged PR 371: irrf page percentage format fixes
* 2023-10-20 (dcf98ce1): irrf page percentage format fixes
* 2023-10-20 (da5dc8b2): Merged PR 366: color changes for legends
* 2023-10-20 (07025dfa): Merged PR 369: Resolve color issues in IRRF
* 2023-10-20 (7960a89e): Resolve irrf issues
* 2023-10-20 (dcb8e281): Merged PR 368: Merge dev into files
* 2023-10-20 (87600414): Merged PR 367: Refactor mappers
* 2023-10-20 (e3510bb7): Update country lookup file
* 2023-10-20 (68cf2330): Removed duplicated field
* 2023-10-20 (0513f6ae): Completed refactoring IRRF mappers
* 2023-10-20 (bc7295cb): Add IRRF file
* 2023-10-20 (9e03fcfe): Resolve test issues
* 2023-10-20 (b8d48be6): Merge branch 'Refactoring/Mappers' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-refactor-mapper-changes
* 2023-10-20 (6b38044b): Refactor impact mapers
* 2023-10-20 (92960135): color changes for legends
* 2023-10-19 (e80bb0a2): Merged PR 95: Deploy
* 2023-10-19 (8c02d7eb): Merged PR 94: Home page
* 2023-10-19 (4b54f02f): Merged PR 365: Home page redesign changes
* 2023-10-19 (0f8d08f7): Home page redesign changes
* 2023-10-19 (679ba423): Merged PR 364: colour scheme updated for Impact page, CO Performance in Meeting IRRF Milesto...
* 2023-10-18 (1bc8edf2): colour scheme updated for Impact page, CO Performance in Meeting IRRF Milestones, indicator score and Homepage IRRF Milestones Met Key statistic
* 2023-10-18 (cbc0fb27): remove console logs
* 2023-10-18 (836061cd): Remove unwanted files and created test folder
* 2023-10-18 (831f0ad6): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-10-18 (c6ec368f): Resolve formatting issues
* 2023-10-18 (8ad1f152): Restructure aydit mapper
* 2023-10-18 (78edaeb3): CHange mappers structure
* 2023-10-17 (5c9b8c36): Refactor home page mapper
* 2023-10-17 (0fd566f2): Refactor home page tests
* 2023-10-17 (df55b269): refactor home mapper
* 2023-10-17 (20bcf6e2): Refactor people mapper
* 2023-10-17 (cba3b7cd): Merge branch 'develop' into Refactoring/Mappers
* 2023-10-17 (c1aef344): Add basic structure
* 2023-10-13 (887894ed): Merged PR 93: Deploy
* 2023-10-13 (4d4fbd93): Merged PR 92: Sync
* 2023-10-13 (09a6d0d5): Merged PR 362: Title changes
* 2023-10-13 (8a266552): Title changes
* 2023-10-13 (50344aa5): Merged PR 360: VALUES\_ANNUAL\_GHG\_EMISSIONS chart changes in greening section
* 2023-10-13 (18e245b9): VALUES\_ANNUAL\_GHG\_EMISSIONS chart changes in greening section
* 2023-10-13 (26477565): Merged PR 359: Resolve year issue
* 2023-10-12 (f00754c7): Resolve year issue
* 2023-10-12 (dacfe7a1): Merged PR 91: Deploy
* 2023-10-12 (43161627): Merged PR 90: Sync
* 2023-10-12 (e0ca08bd): Merged PR 358: Added Vacant Post, Posisition Management by bureau and Vacancy Rate
* 2023-10-12 (ce1a278b): resolved merge conflict
* 2023-10-12 (df27fd41): fixed issue in tooltips in current vacancy rate by bureau and added current vacancy rate by bureau and Posistion management by bureau to vacancy rate page
* 2023-10-12 (0357f091): Merged PR 356: Increase the height of “Comments on IFD Data” widget to make align some widge...
* 2023-10-12 (160991f9): Increase the height of “Comments on IFD Data” widget to make align some widgets in financial section
* 2023-10-12 (088c4ebc): Merge branch 'changes' into vacant-post
* 2023-10-12 (d0d18582): moved current vancancy by bureau to common charts
* 2023-10-12 (69df6f1f): Merged PR 355: Add annual GHG total stat
* 2023-10-12 (5d4a2835): Add annual GHG total stat
* 2023-10-11 (8972a3b3): Merged PR 89: Deploy
* 2023-10-11 (1f5c5c03): Merged PR 88: Sync
* 2023-10-11 (0d941d16): Merged PR 354: Distribution of Total IFD score color changes
* 2023-10-11 (40e2e9ad): Distribution of Total IFD score color changes
* 2023-10-11 (888a8b03): Merged PR 352: removed % showing in country audit ratings
* 2023-10-11 (6c44e4be): removed % showing in country audit ratings
* 2023-10-11 (ea181d94): Merged PR 351: percentage of top 10 deliveries added
* 2023-10-11 (90338da2): integrated with BE
* 2023-10-11 (d11053c8): added vacant post graph
* 2023-10-11 (ee188068): Merged PR 350: Add total to response
* 2023-10-11 (aeb5c1a6): Add total to response
* 2023-10-11 (8e7115e4): deleted EmissionsGraphCard
* 2023-10-11 (aee1602f): created PieChartLabel component and moved EmissionsGraphCard logic to it
* 2023-10-11 (1bac51e6): Merged PR 349: BE: Percentage of Top 10 Deliveries of Total for Each Year
* 2023-10-11 (be7129ab): Merged PR 348: Change IFD 2023 data
* 2023-10-11 (2f94395a): Merge branch 'develop' into PERF-179
* 2023-10-11 (ac95034e): Change IFD 2023 data
* 2023-10-11 (8d4dd2e9): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-172-be
* 2023-10-11 (e0e5f0a7): BE: Percentage of Top 10 Deliveries of Total for Each Year
* 2023-10-11 (084fcfa6): Merged PR 347: Change audit positive rating methodology..
* 2023-10-11 (287a776c): Change IFD scores
* 2023-10-11 (fccd1b71): Merge branch 'develop' into PERF-176
* 2023-10-11 (02a191a0): Change positive audit rating methodology
* 2023-10-10 (e9d6ea91): Merged PR 87: Deploy
* 2023-10-10 (d6a0d68b): Merged PR 86: Sync
* 2023-10-10 (bd90dd0b): added Percentage of Top 10 deliveries of Total for Each Year
* 2023-10-10 (96ec28ec): Merged PR 346: Add " Vacant Post by Bureau" Filter
* 2023-10-10 (a60d7f22): Merged PR 345: added comments on ifd data note card
* 2023-10-10 (9e82ca9c): Merge branch 'develop' into PERF-176
* 2023-10-10 (08b34a91): Add background colors
* 2023-10-10 (d415d190): Add "Vacant Post by Bureau" Indicator
* 2023-10-10 (f33b5fab): resolved merge conflict
* 2023-10-10 (ef26226f): added comments-on-ifd-data
* 2023-10-10 (d227b968): Merged PR 343: refactored filter changes in efficiencyMapper file
* 2023-10-10 (c7e0e7c2): Merged PR 342: extracted common charts
* 2023-10-10 (9015ab38): Merged PR 341: added filters to distribution of total ifd scores graph
* 2023-10-10 (abe128c5): refactored filter changes in efficiencyMapper file
* 2023-10-10 (9e0d80ce): extracted gender distributiob by position to commonCharts
* 2023-10-10 (2b9c8d09): commonGraphs
* 2023-10-10 (1437d6c1): extracted totol emission by year with trendline to commonGraphs
* 2023-10-10 (2c70eea3): extracter total delivery vs targets per year graph into commmonCharts
* 2023-10-10 (0b37c8b7): added commonCharts
* 2023-10-10 (a6c97b4b): extracted total ifd to commonCharts
* 2023-10-10 (5fd3b8b1): replaced COPerformance chart in IRRF page with the commonCharts/COPerformance
* 2023-10-10 (62e3e592): added filters to distribution of total ifd scores graph
* 2023-10-10 (17d5887f): moved AuditPage -> AccountabilityPage/AuditPage
* 2023-10-10 (410ba12b): Merged PR 340: Add bureau filter to latest IFD scores Indicator
* 2023-10-10 (14ef9164): created common charts for Impact
* 2023-10-10 (6045af57): extracted COPerformance chart to commoncharts
* 2023-10-10 (7c0d22e3): Remove console logs
* 2023-10-10 (996ef47a): Merge branch 'develop' into PERF-168
* 2023-10-10 (7b4a65b4): Add filtering to lattest IFD scores
* 2023-10-10 (ccc82ba4): Merged PR 338: Improve filtering
* 2023-10-10 (e3b18d7a): Merged PR 339: Fixed issue in trend line not updating correctly
* 2023-10-10 (f01934c7): updated
* 2023-10-09 (6bfca0ca): Refactor filtering options
* 2023-10-06 (878f7a6a): Merged PR 85: Deploy
* 2023-10-06 (7010ecb6): Merged PR 84: Sync
* 2023-10-06 (ae06f1d3): Merged PR 337: added filters to greening moonshots page
* 2023-10-06 (b25bc571): added filters
* 2023-10-06 (de26e33d): Merged PR 336: Add category filters.
* 2023-10-06 (c5e2f130): Add catgory filters
* 2023-10-06 (3569a4da): Merged PR 334: fix issues in UI
* 2023-10-06 (36ec4fe1): Merged PR 335: CO Performance in Meeting IRRF Milestones map changes
* 2023-10-06 (99bd80b7): removed the commented layer in map
* 2023-10-06 (d6321203): fixed issues with filters and some styling issues
* 2023-10-06 (4dfa798c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-152-changes
* 2023-10-06 (c28ff2de): removed unnecessary console.log
* 2023-10-05 (2f5ba9e8): changed the title for Proportion of Positive Audit Rating Results table
* 2023-10-05 (865efb0a): removed the padding added by detailList
* 2023-10-05 (2185426e): reduced the space between titles and tables
* 2023-10-05 (9b3253c3): updated
* 2023-10-05 (b88f8eb0): fixed the alignment issues in tables and issues in text cards
* 2023-10-05 (af398650): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into changes
* 2023-10-04 (612beebb): Merged PR 83: Deploy UAT
* 2023-10-04 (ba2ce754): Merged PR 82: Issue fixes
* 2023-10-04 (029092b9): Merged PR 332: emissions by cat filter changes
* 2023-10-04 (01106507): emissions by cat filter changes
* 2023-10-04 (de22cd36): fixed issue in header getting cutt offed
* 2023-10-04 (ac3ee09d): Merged PR 331: Resolve filtering issue
* 2023-10-04 (6d2f7732): Resolve filtering issue
* 2023-10-04 (9a1ecccd): Merged PR 81: Deploy UAT
* 2023-10-04 (e2c2d76b): Merged PR 80: Sync
* 2023-10-04 (b6aad0e5): Merged PR 330: Resolve filtering issues
* 2023-10-04 (ee6122c4): Resolve filtering issues
* 2023-10-04 (79326b5c): Merged PR 328: added percentage of targets of met chart
* 2023-10-04 (70c66445): Merged PR 325: Add filters to greening moonshot.
* 2023-10-04 (fda3c660): inegrated with BE
* 2023-10-04 (cdfd76a0): Merged PR 327: lint issues fixes
* 2023-10-04 (ca777e53): lint issues fixes
* 2023-10-04 (842a18e8): Merged PR 326: EFFICIENCY\_TARGETS\_MET\_EACH\_MONTH backend changes and delivery handler file c...
* 2023-10-04 (755f91e9): EFFICIENCY\_TARGETS\_MET\_EACH\_MONTH backend changes and delivery handler file changes
* 2023-10-04 (7c3acfaf): added backgroundColor for the chart points
* 2023-10-03 (bd4eb75f): updated
* 2023-10-03 (e588bbdc): updated
* 2023-10-03 (32e48231): Add filters to greening moonshot
* 2023-10-03 (0ff3e0d6): Merged PR 324: added total ifd num countries graph to integrated financial dashboard page
* 2023-10-03 (1112f5ad): added graph
* 2023-10-03 (d46b27b3): added basic graph
* 2023-10-03 (a3dac080): added basic graph for percentage-of-targets-met
* 2023-10-03 (fae71dbf): Merged PR 322: dynamically adjust the left position of tooltip model in engagement history index
* 2023-10-03 (53426584): Merged PR 321: Fixed the legend marker responsive issue in accountability page
* 2023-10-02 (24cf0762): updated
* 2023-10-02 (a0a3c997): added comments, and updated
* 2023-10-02 (3a201670): fixed issue in right most tooltip model getting cut offed in smaller screen
* 2023-10-02 (798e8d76): Fixed the legend marker responsive issue in accountability page

### September

* 2023-09-27 (3b10120c): Merged PR 79: Deploy
* 2023-09-27 (d5bfb11c): Merged PR 78: Sync
* 2023-09-27 (f4449577): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-27 (fa71a4f5): Merged PR 318: navigate onclick breadcrumb
* 2023-09-27 (3c43890a): resolved merge conflict
* 2023-09-27 (6f7a22d5): Merged PR 301: \[Inprogress] merge dev into files
* 2023-09-27 (fe0c8a03): Merged PR 317: {Inprogress] Refactor Mappers
* 2023-09-27 (a3ac6925): Merged PR 316: added support for custom environment variables
* 2023-09-27 (2111e1de): Merged PR 315: Added graph for distribution of total ifd scores
* 2023-09-27 (bd92e9e8): updated
* 2023-09-27 (2e463cf2): navigate onClick on breadcrumb
* 2023-09-27 (bc1370e5): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-09-27 (3e089cbb): Refactor Mappers
* 2023-09-27 (1ab7fde5): added support for custom environment variables
* 2023-09-27 (5073ee16): updated
* 2023-09-27 (8db39c9d): deleted dummyData.ts for financial page
* 2023-09-27 (c8c39ad2): updated the ticks format
* 2023-09-27 (36dfa063): updated strings
* 2023-09-27 (158233a8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into distribution-of-total-ifd-scores
* 2023-09-27 (82e02a58): added curve for distribution of total ifd scores
* 2023-09-27 (06715334): updated
* 2023-09-27 (03738644): Merge branch 'distribution-of-total-ifd-scores' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into distribution-of-total-ifd-scores
* 2023-09-27 (a6b635c0): updated
* 2023-09-27 (825c4a50): updated
* 2023-09-26 (e2663a7a): Merged PR 313: responsive issue fixes
* 2023-09-26 (6e17627c): responsive issue fixes
* 2023-09-26 (90fca25d): Merged PR 311: Fixed the mobile responsive issue in view indicator btn
* 2023-09-26 (9dff7013): Fixed the mobile responsive issue in view indicator btn
* 2023-09-26 (347e7c51): Merged PR 310: Add points to audit mapper
* 2023-09-26 (75c598ce): Add points to audit mapper
* 2023-09-26 (b602915c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into distribution-of-total-ifd-scores
* 2023-09-26 (76091879): Merged PR 308: FE: Country Office Capacity by Score changes
* 2023-09-26 (1a14e0b1): updated
* 2023-09-26 (18a7c517): Merged PR 309: added token
* 2023-09-26 (d2da353f): Merged PR 306: distribution of ifd scores
* 2023-09-26 (2aa7c332): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-154-changes
* 2023-09-26 (d272c9f2): updated
* 2023-09-26 (4f94f0c4): HOME\_SCORE\_CAPACITY integrations
* 2023-09-26 (808b1977): Merged PR 307: Add authorization
* 2023-09-26 (1c618e9b): added token
* 2023-09-26 (e1a55a19): Add authorization
* 2023-09-26 (db641017): basic graph for ifd done without curve
* 2023-09-26 (99eba333): Merged PR 305: Refactor home stats
* 2023-09-26 (99b8c8a4): Refactor home stats
* 2023-09-26 (2e439896): FE: Country Office Capacity by Score changes
* 2023-09-26 (35023de3): resolved merge conflict
* 2023-09-26 (e828d32a): Merged PR 304: Add home page stat(PERF-155)
* 2023-09-26 (fb2e1a69): Merge branch 'develop' into PERF-155
* 2023-09-26 (b4eafaf3): Add country office capacity by score
* 2023-09-25 (d46e5426): Merged PR 77: Deploy
* 2023-09-25 (2d9f90b0): Merged PR 76: Sync
* 2023-09-25 (72d67e7d): Merged PR 302: integrated with BE and added graph for average ifd across year
* 2023-09-25 (cc73efdf): updated
* 2023-09-25 (72d6c62b): Merged PR 300: Resolve label names issue
* 2023-09-25 (2badea56): Resolve label names issue
* 2023-09-25 (654a31c6): integrated average ifd score per year graph with BE
* 2023-09-25 (f8c57331): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into countries-with-largest-score-increase
* 2023-09-25 (4444ac40): added data and basic table for average ifd score per yr
* 2023-09-25 (e72c0b01): Merged PR 299: Add IFD Avg from years
* 2023-09-25 (efcd11cf): getting data from BE for largest score decrease
* 2023-09-25 (88cb6a81): CO Performance in Meeting IRRF Milestones map changes
* 2023-09-25 (c6cc3d90): CO Performance in Meeting IRRF Milestones map component label changes
* 2023-09-25 (e984b4f9): Remove stats
* 2023-09-25 (1703e3b3): Add IFD Avg from years
* 2023-09-25 (a9e4d3aa): updated
* 2023-09-25 (cbb9e2b1): connected Largest score graph with BE
* 2023-09-25 (59a06be9): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into countries-with-largest-score-increase
* 2023-09-25 (f7da180b): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into distribution-of-total-ifd-scores
* 2023-09-25 (e3f0c835): updated
* 2023-09-22 (cfbd3479): Merged PR 75: Deploy
* 2023-09-22 (6ee6186e): Merged PR 74: Sync
* 2023-09-22 (cee5989c): Merged PR 297: updated padding and top margin of url btn in data card
* 2023-09-22 (0b7016ab): updated padding and top margin of url btn in data card
* 2023-09-22 (abe45038): updated
* 2023-09-22 (13e29682): Merged PR 296: Add IFD stats
* 2023-09-22 (d970b123): Merged PR 295: Deploy files
* 2023-09-22 (79757eb1): Merged PR 292: added highest avg ifd table and lowest avg ifd table
* 2023-09-22 (08416966): Merged PR 293: Efficiency endpoint changes
* 2023-09-22 (896be5f7): Improve test cases
* 2023-09-22 (8ef8a1ea): Merge branch 'data-mig-changes' into PERF-40
* 2023-09-22 (969e626f): Add IFD related stats
* 2023-09-22 (517071d5): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-22 (d2aea50a): EFFICIENCY\_TOT\_CONTRIBUTIONS stat endpoint fixes
* 2023-09-22 (72a22ed2): Merged PR 72: Deploy
* 2023-09-22 (8827bfed): Merged PR 70: Sync
* 2023-09-22 (7d09702d): Merge branch 'develop' into pr26
* 2023-09-22 (add811b8): Merge branch 'data-mig-changes' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-22 (5a397556): EFFICIENCY\_MONTH\_REV stat endpoint changes
* 2023-09-21 (fa2b132d): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into countries-with-largest-score-increase
* 2023-09-21 (c2439f48): removed unnecessary console.logs
* 2023-09-21 (35fdb8f7): added table for ten countries with lowest avg scores across 2020-2022
* 2023-09-21 (3f520990): added table for ten countries with highest avg scores across 2020-2022
* 2023-09-21 (f4da26af): Add positive rating stat
* 2023-09-21 (eba23b42): EFFICIENCY\_CUMULATIVE\_AVG stat endpoint changes
* 2023-09-21 (22dd455e): Merge branch 'data-mig-changes' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-21 (79271cb9): EFFICIENCY\_TOT\_CONTRIBUTIONS stat endpoint changes
* 2023-09-21 (461cfad7): Merged PR 288: added links for sub pages
* 2023-09-21 (b3cbde8a): Merged PR 290: Add accountability stats
* 2023-09-21 (97eb25f7): Merged PR 289: Added graph for countries with largest score increase
* 2023-09-21 (b0211f47): Complete audit page
* 2023-09-21 (3c66a0d3): added graph for largest score decrease
* 2023-09-21 (248f8ee6): added graph for countries with largest score increase
* 2023-09-20 (d13677ee): EFFICIENCY\_TOT\_DEL\_TARGET stat mapping changes in efficiency mapper
* 2023-09-20 (20279226): basic graph done
* 2023-09-20 (35d7ae28): basic graph done
* 2023-09-20 (0ec0aa3c): added links for sub pages
* 2023-09-20 (21e1f41c): Merged PR 287: increased padding of url btn
* 2023-09-20 (e62fb3d0): increased padding of url btn
* 2023-09-20 (e4175050): Merged PR 285: refactored, created constants for methodology colors and updated
* 2023-09-20 (9302e6e1): updated colors and constants for lates country office performance audit rating
* 2023-09-20 (469b3496): updated
* 2023-09-20 (34e7ed06): resolved merge conflict
* 2023-09-20 (f557e973): updated
* 2023-09-20 (ce73360c): updated
* 2023-09-20 (86fa6b40): Merged PR 284: Change parameter
* 2023-09-20 (9abb3756): Change parmeter
* 2023-09-20 (87b88ba2): Merged PR 281: \[InProgress] Refactor file structures
* 2023-09-20 (33bc2016): Merge branch 'data-mig-changes' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-20 (b8a9f80a): Add mappers
* 2023-09-20 (24908455): Merged PR 182: add url btn
* 2023-09-20 (f354b2cf): resolved merge conflicts
* 2023-09-20 (b8264b93): Merged PR 278: stopped re rendering of map in impact page.
* 2023-09-20 (71609bdf): removed unnecessary files
* 2023-09-20 (5b18a507): Merge branch 'data-mig-changes' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-20 (94ba4f4f): vacancyFIle handler changes
* 2023-09-20 (bdd0cdec): Change config
* 2023-09-20 (5a8022ca): Resolve lint and test issues
* 2023-09-20 (275ff0b2): Merge branch 'data-mig-changes' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-20 (0b24e265): Merge branch 'develop' into data-mig-changes
* 2023-09-19 (c36df334): Remove deps
* 2023-09-19 (39d79eca): Fix CICD issue
* 2023-09-19 (828b9d66): Updated azure-pipelines\_filecopy.yml
* 2023-09-19 (9dc77b90): Updated .env.production
* 2023-09-19 (cef8ef76): Updated azure-pipelines\_filecopy.yml
* 2023-09-19 (e5d3bbd6): Merged PR 69: Latest
* 2023-09-19 (9b0d478d): Merged PR 67: Merged PR 66: Deply
* 2023-09-19 (694aa86b): Merged PR 66: Deply
* 2023-09-19 (1423a288): Merge branch 'staging' into develop
* 2023-09-19 (2c5a7eac): Merged PR 65: sync
* 2023-09-19 (6cb307bb): resolve lint issue
* 2023-09-19 (944d0be3): Add raw to config
* 2023-09-19 (5989c48d): resolve isseue
* 2023-09-19 (51fac783): Resolve issue
* 2023-09-19 (53ec7d9e): Updated .env.development
* 2023-09-19 (18415383): Merged PR 280: Resolve issue
* 2023-09-19 (e870077b): resolve issues
* 2023-09-19 (bad67264): Resolve issues
* 2023-09-19 (d869220d): Resolve file issue
* 2023-09-19 (7a8f586a): Merged PR 279: Update csv reads
* 2023-09-19 (302ed208): Update csv
* 2023-09-19 (b3c8542d): Add logs
* 2023-09-19 (0c616094): Add logs
* 2023-09-19 (2ba51cff): Add console logs
* 2023-09-19 (5f7cb9ef): Add extra logs
* 2023-09-19 (64fed005): Resolve lint issues
* 2023-09-19 (0d8f3adb): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into develop
* 2023-09-19 (f9a98f19): Add console.logs
* 2023-09-19 (8267f92a): file handler function changes regarding updateProcessedFile
* 2023-09-19 (7e05db2c): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-09-19 (9d101f15): Resolve lint issues
* 2023-09-19 (6e592c0b): Add console logs
* 2023-09-19 (3cccbb62): updated
* 2023-09-19 (c8f8c9b6): fixed map rerendering on state changes
* 2023-09-19 (bc8754de): Updated .env.development
* 2023-09-19 (fbbc52c9): Add file updating logic
* 2023-09-19 (fe3f0c26): Updated .env.development
* 2023-09-19 (452a1571): Merge branch 'file-structure' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-19 (edcc0ed4): Updated .env.development
* 2023-09-19 (9853666c): file handler function changes
* 2023-09-19 (0c2b96a4): Merged PR 63: Deploy
* 2023-09-19 (9b1b573b): Merged PR 62: Sync
* 2023-09-19 (d1d2b0b1): Merged PR 277: Update azure-pipelines-files.yml for Azure Pipelines
* 2023-09-19 (1526e9bd): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-09-19 (b7f317b5): Merged PR 275: Update azure-pipelines-files.yml for Azure Pipelines
* 2023-09-19 (b42be48f): Merged PR 276: Change files directory
* 2023-09-19 (72a8c7e5): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-09-19 (c5a62c6d): Change files directory
* 2023-09-19 (9f9e5b0f): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-09-19 (12ffb5f0): Update azure-pipelines-files.yml for Azure Pipelines
* 2023-09-19 (e09afe06): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into data-mig-changes
* 2023-09-19 (3a72ca90): file handler functions for UNDP delivery analysis, qaCompletion Handler and vacancyRateHandler
* 2023-09-18 (1f2fd60f): Merged PR 61: Deploy main
* 2023-09-18 (c0a7cb62): Updated .env.development
* 2023-09-18 (0b263c66): Merged PR 274: merge dev into files
* 2023-09-18 (5f68c090): Updated function.json
* 2023-09-18 (0304ac65): Updated .env.development
* 2023-09-18 (74730f4e): Merged PR 59: Deploy
* 2023-09-18 (0b23e88e): Merged PR 58: Deploy
* 2023-09-18 (a8a6b639): Merged PR 273: Add historic data file
* 2023-09-18 (1f91b5ea): Add historic data file
* 2023-09-18 (2793529a): Merged PR 271: made the maps to refresh only when it's states are changed
* 2023-09-18 (5d82988f): made the maps to refresh only when it's states are changed
* 2023-09-18 (483bba14): Set up CI with Azure Pipelines
* 2023-09-18 (8c41ac63): Merged PR 270: merge dev into files
* 2023-09-18 (f01e3b34): Merged PR 269: Resolve file issues
* 2023-09-18 (62d67c5f): Resolve lint issues
* 2023-09-18 (c2009e18): Merged PR 267: removed extra tick at the end of x axis in cumulative graph and updated styling of dropdown
* 2023-09-18 (9218318c): updated
* 2023-09-18 (b08a50d3): Merged PR 57: Latest changes
* 2023-09-18 (26425217): Updated .env.development
* 2023-09-18 (e29dd280): Change configs
* 2023-09-18 (42d86ea1): Add files
* 2023-09-18 (35a378db): Merge branch 'develop' into file-structure
* 2023-09-18 (9420239a): Add files
* 2023-09-18 (2af00be1): updated
* 2023-09-18 (58c6fb07): added padding between filters in dropdown
* 2023-09-18 (df6bb453): removed extra tick in x-axis of cumulative trend graph
* 2023-09-18 (690b5bfc): Updated .env.development
* 2023-09-18 (00f5b74f): Merged PR 56: Deploy
* 2023-09-18 (643025bf): merge conflict resolved
* 2023-09-18 (59e29987): Merged PR 54: Latest
* 2023-09-18 (36f9dd3f): Merged PR 266: Add files
* 2023-09-18 (3bce66b6): Add new files
* 2023-09-18 (9388f125): Add updated files
* 2023-09-18 (f3e2875d): Merged PR 265: Updated filter dropdown design
* 2023-09-18 (e78ee6cb): updated styling for filter drop down
* 2023-09-18 (e8219019): resolved merge conflict
* 2023-09-18 (8b14209c): updated the logic for filters in inner pages
* 2023-09-18 (2a39d61e): Add template for all the files
* 2023-09-18 (7bf13068): updated filter logics in main pages
* 2023-09-18 (288d6728): Update connection string
* 2023-09-18 (fdff1ac8): Fix name issue
* 2023-09-18 (2b5b7b9d): Update CICD trigger files
* 2023-09-18 (4b61121b): Update cicd
* 2023-09-18 (ca01f495): Revert "Revert "Update deployments""
* 2023-09-18 (870afbf5): Revert "Revert "Prod build""
* 2023-09-18 (0019c5a1): Merged PR 52: Prod deploy
* 2023-09-18 (3219da0f): Revert "Prod build"
* 2023-09-18 (c5d8ad0a): Revert "Update deployments"
* 2023-09-18 (736f8a90): Update deployments
* 2023-09-18 (be01f750): Prod build
* 2023-09-15 (f4c5fe13): updated
* 2023-09-15 (b76efd81): Merge branch 'develop' into file-structure
* 2023-09-15 (17c13cf4): Add basic structure
* 2023-09-15 (4c230a60): Merged PR 264: Cumulative Average Month-by-Month Trendline with September 2023 Highlight BE...
* 2023-09-15 (7d96507a): Cumulative Average Month-by-Month Trendline with September 2023 Highlight BE changes
* 2023-09-15 (c23991d4): updated
* 2023-09-15 (36f5ed0d): updated graph to use timestamps
* 2023-09-14 (7dc8e406): Merged PR 50: Deploy
* 2023-09-14 (9161f2d3): Merged PR 49: Change colors
* 2023-09-14 (5100d5c8): Change colors
* 2023-09-14 (2616618c): Merged PR 48: Deploy
* 2023-09-14 (9d29c061): Merged PR 47: Deploy
* 2023-09-14 (3f5b1161): Merged PR 263: tooltip issue fixed
* 2023-09-14 (a347391c): tooltip issue fixed
* 2023-09-14 (0dd63597): Merged PR 46: Deploy
* 2023-09-14 (6dcdd959): Merged PR 45: Latest
* 2023-09-14 (1d184f29): Merged PR 261: Fixed the tooltip text issues in QA Completion Rates for Projects in the Desi...
* 2023-09-14 (1e7a022d): Fixed the tooltip text issues in QA Completion Rates for Projects in the Design Stage (2019 - 2022)
* 2023-09-14 (6f3092f9): Merged PR 260: update function to determine color for resources mobilized
* 2023-09-14 (add92c36): update function to determine colr for resources mobilized
* 2023-09-14 (b3a7abec): updated styles
* 2023-09-14 (e9c5816f): Merged PR 44: Deploy
* 2023-09-14 (351e7291): Merged PR 43: Latest
* 2023-09-14 (f0f3135c): resolved merge conflict
* 2023-09-14 (91a1dced): Merged PR 258: Resolve negative value issue
* 2023-09-14 (bc954e67): Merged PR 257: changes done
* 2023-09-14 (c851daf8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into changes
* 2023-09-14 (15ba3108): changes done
* 2023-09-14 (2d8a5fab): Resolve negative value issue
* 2023-09-14 (ff13b406): Merged PR 256: passed data change for QA Completion Rates for Projects in the Design Stage (...
* 2023-09-14 (5afeb22c): Merged PR 255: added SESP score, added Cumulative Average Month-by-Month Trendline, showing indicator scores
* 2023-09-14 (ec0cdc37): passed data change for QA Completion Rates for Projects in the Design Stage (2019 - 2022)
* 2023-09-14 (2383207f): added indicator scores'
* 2023-09-14 (250b9f91): changed bureaus -> bureau in getting filters
* 2023-09-14 (ba21ac6e): resolved merge conflict
* 2023-09-14 (f11fccc6): update title constants
* 2023-09-14 (07656fbf): added title
* 2023-09-14 (b4ada321): updated
* 2023-09-14 (e4d2cc9d): changed bureaus -> bureau
* 2023-09-14 (fc8abff3): Merged PR 252: Number of Countries in Each Area Based on Total IFD Scores (2020 - 2023) titl...
* 2023-09-14 (798c18b3): Merged PR 253: Refactor test cases
* 2023-09-14 (7839a5de): updated
* 2023-09-14 (07807f27): Refactor test cases
* 2023-09-14 (61efcf4e): Merged PR 251: resolve test issues
* 2023-09-14 (449c4745): resolve test issues
* 2023-09-14 (d9eaeaa6): Merged PR 250: Resolve efficiency issues
* 2023-09-14 (dda91dcc): Resolve lint issues
* 2023-09-14 (6e6be582): complete efficiency issues
* 2023-09-14 (3649fd2b): Uncommented lines
* 2023-09-14 (fc2f041f): resolve qa issue
* 2023-09-14 (001a4828): Merged PR 249: Added the indicator score for UNDP’s Aid Transparency Rank and Score in value...
* 2023-09-14 (e0ab7c31): Added the indicator score for UNDP’s Aid Transparency Rank and Score in values page
* 2023-09-14 (584f8bba): updated value for SESP Completion
* 2023-09-14 (fdfc1d99): Merge branch 'develop' into PERF-100
* 2023-09-14 (45fc259b): Update induvidual scores
* 2023-09-14 (e2d844ab): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into changes
* 2023-09-14 (0c376bdb): added some styling and did some changes
* 2023-09-14 (913b8f2b): Merged PR 248: changes in efficiency test file
* 2023-09-14 (40b085dc): Number of Countries in Each Area Based on Total IFD Scores (2020 - 2023) title and description changes
* 2023-09-14 (e79f213d): Merge branch 'develop' into PERF-100
* 2023-09-14 (ed2b835e): Change label
* 2023-09-14 (dc094779): changes in efficiencyMapper file
* 2023-09-14 (a6cdb3ca): changes in efficiency test file
* 2023-09-14 (fdb46572): added links for 'For Your Information' section
* 2023-09-14 (e3e676ca): basic changes
* 2023-09-14 (fa4c816d): Merged PR 247: added undp aid trans score in NAV STATS
* 2023-09-14 (c7f4bc3a): added undp aid trans score in NAV STATS
* 2023-09-13 (a1bb062d): Merged PR 42: Deploy
* 2023-09-13 (2e8bbed7): Merged PR 41: Text changes
* 2023-09-13 (09122250): Merged PR 243: removed USG and data for USG from gender distribution by position graph
* 2023-09-13 (9a2df7a3): Merged PR 245: title change for SH and SEA survey graph
* 2023-09-13 (1135da08): Merged PR 244: Refactor test cases
* 2023-09-13 (05247238): title change for SH and SEA survey graph
* 2023-09-13 (874ce498): Refactor test cases
* 2023-09-13 (cbc4951f): Merged PR 40: Deploy
* 2023-09-13 (f8e85fbb): Merged PR 39: Sync
* 2023-09-13 (e7755cda): Merge branch 'develop' into pr10
* 2023-09-13 (39a73415): removed USG and data for USG from gender distribution by position graph
* 2023-09-13 (c056e4d3): Merged PR 241: Added filtering for graphs in inner pages, refactored, improved logic for calculating min and max for graph y-axis
* 2023-09-13 (58fad940): removed greeting and added headerscores avg to global header box
* 2023-09-13 (a3502145): refactored
* 2023-09-13 (4a62dd45): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into changes
* 2023-09-13 (e34c992d): Merged PR 240: home page stat cards rate color changes
* 2023-09-13 (8144c9d0): Merged PR 238: Completed delivery stat
* 2023-09-13 (51ef45ef): Merged PR 239: Update SH and SEA
* 2023-09-13 (c65814a2): home page stat cards rate color changes
* 2023-09-13 (4909b8ec): Completed the delivery handler
* 2023-09-13 (7cd113af): Update SH and SEA
* 2023-09-13 (61256612): Update naming
* 2023-09-13 (722fe7da): Add a readme
* 2023-09-13 (bbd2884e): added filtering for total deliveries vs targets per year in delivery page
* 2023-09-13 (f73861f2): removed unnecessary console.log
* 2023-09-13 (2b00e5d7): added filtering to total emmisions by year with trend line in greening page
* 2023-09-13 (1605c7be): Merged PR 237: Add delivery stat
* 2023-09-13 (9c38643f): Refactor test cases
* 2023-09-13 (155e0cc4): Add nav stat
* 2023-09-13 (294fdfb5): Resolve lint issues
* 2023-09-13 (79460ee7): ADd delivery stat
* 2023-09-13 (a72d3420): Merged PR 235: Updated Homepage Legends
* 2023-09-13 (da1dd1cd): Merged PR 234: Add authorization
* 2023-09-13 (aa1ea34f): Updated Homepage Legends
* 2023-09-13 (312dcc2d): Add env files
* 2023-09-13 (ebe32860): Update server.yml
* 2023-09-13 (ddf2b115): Achange package.json
* 2023-09-13 (55993cfa): Merge branch 'develop' into PERF-116
* 2023-09-13 (c2d767f6): Add env files and configs
* 2023-09-12 (17c47508): Merged PR 233: updated title of total carbon footprint per office
* 2023-09-12 (ab6ec51d): updated title of total carbon footprint per office
* 2023-09-12 (c73d2f3c): Merged PR 37: Deploy
* 2023-09-12 (889b7968): Merged PR 36: Text Changes
* 2023-09-12 (36e51b48): Merged PR 232: updated Institutional Revenue graph max values
* 2023-09-12 (915c5d6e): updated Institutional Revenue graph max values
* 2023-09-12 (9f4fe310): Merged PR 229: font size change for title in methodology section
* 2023-09-12 (d21ab3eb): Merged PR 230: Updated texts for stat cards
* 2023-09-12 (0a7babeb): Updated texts for stat cards
* 2023-09-12 (8f635b0b): font size change for title in methodology section
* 2023-09-12 (f0c8f474): Merged PR 35: Deploy
* 2023-09-12 (bbbdf717): Merged PR 34: Sync
* 2023-09-12 (ec810d95): Merged PR 226: Update Engagement Historical Trend data
* 2023-09-12 (39a8f732): Merged PR 227: added filters for impact, accountability, efficiency and values page
* 2023-09-12 (ad5fc0c4): updated
* 2023-09-12 (aa172150): Update Engagement Historical Trend data
* 2023-09-12 (6dd6c54a): Merged PR 222: \[Inprogress] Resolve missing values in country lookup
* 2023-09-12 (f7f00c55): added filter for total emissions by year with trend line
* 2023-09-12 (108e4afd): added filter for ICPE AVG
* 2023-09-12 (48a5b015): Merged PR 223: Methodology page changes
* 2023-09-12 (c9c4da83): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-130-changes
* 2023-09-12 (3124050d): Methodology page changes
* 2023-09-12 (390a17e3): Resolve missing values in country lookup
* 2023-09-12 (d8b23bda): Merged PR 220: Refactor test cases
* 2023-09-12 (b1709d6c): Resolve lint issues
* 2023-09-12 (06e7d757): Resolve ICPE\_AVG filterset issue
* 2023-09-12 (3e74875d): updated
* 2023-09-12 (dc5ed99d): removed unnecesary console.logs
* 2023-09-12 (36973e6d): removed filtering from QA completion graph and removed some unnecessary console.logs
* 2023-09-12 (31ece680): Latest Audit Rating table filtering added
* 2023-09-12 (5f921383): Merged PR 218: Added filter for total ifd graph in accountability page
* 2023-09-12 (bfb3356a): Merged PR 219: Resolve issues in testing and filtering.
* 2023-09-12 (ccf492b2): Merge branch 'develop' into PERF-116
* 2023-09-12 (05f64329): Resolve issues in testing and filtering
* 2023-09-11 (69190719): updated
* 2023-09-11 (e5e29367): updated NUM\_COUNTRIES
* 2023-09-11 (f525c241): Merged PR 217: Add filter values
* 2023-09-11 (aadff263): Add filter values
* 2023-09-11 (59f27c14): Merged PR 216: Complete efficiency page filters
* 2023-09-11 (0d4fc9c4): Complete efficiency page filters
* 2023-09-11 (f09eff43): Merged PR 33: Deploy
* 2023-09-11 (c82374e9): Merged PR 32: Deploy
* 2023-09-11 (a0fee056): Merged PR 215: Refactor efficiency filters
* 2023-09-11 (24e0bf7d): updated
* 2023-09-11 (19abf898): update function.json
* 2023-09-11 (c4a2e27b): Resolve test issue
* 2023-09-11 (dfd380e0): Resolve test failiure
* 2023-09-11 (b9e8720e): Improve efficiency
* 2023-09-11 (9925fc30): Refactor efficiency filters
* 2023-09-11 (585c49d3): Merged PR 213: Updated legend for Number of Countries in Each Area Based on Total IFD Scores...
* 2023-09-11 (eb0aa2ce): Updated legend for Number of Countries in Each Area Based on Total IFD Scores (2020 - 2023)
* 2023-09-11 (6525e32d): AUDIT\_NUM\_COUNTRIES filtering done
* 2023-09-11 (a045236c): Merged PR 212: Fixed the navigation bar color issue while entering the url manually
* 2023-09-11 (c1c11267): Fixed the navigation bar color issue while entering the url manually
* 2023-09-11 (51d3edb6): resolved merge conflict
* 2023-09-11 (385ce120): resolved merge conflict
* 2023-09-11 (06177630): updated
* 2023-09-11 (deba79b5): Merged PR 210: Update Green Energy Moonshot and Accountability page according to BE changes
* 2023-09-11 (91e3bd4c): Merged PR 211: Change to lattest year
* 2023-09-11 (ebab6211): remove commented lines
* 2023-09-11 (75efa13e): Change to lattest year
* 2023-09-11 (1de0e541): fixed issue in AccountabilityPage
* 2023-09-11 (42153393): Merged PR 209: FIxed the min width issue in graphs in small screen sizes
* 2023-09-11 (00bbaaae): FIxed the min width issue in graphs in small screen sizes
* 2023-09-11 (1b8eabaf): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into changes
* 2023-09-11 (7c32a3e9): update moonshots graph done
* 2023-09-11 (ce254a4a): Merged PR 208: Change the body structure
* 2023-09-11 (77a69f98): Chage the structure of the response
* 2023-09-11 (03a58d71): Change the body structure
* 2023-09-11 (ba274ce4): updated
* 2023-09-11 (1c93af75): Merged PR 207: Resolve auditmapper filtering issues
* 2023-09-11 (690f7e65): Correscted countries word
* 2023-09-11 (eb24ec26): Change filter values
* 2023-09-11 (e964810e): Merge branch 'develop' into PERF-116
* 2023-09-11 (fc5af1cc): Add efficiency stat filtering
* 2023-09-11 (75294cb6): basic changes for integration with backend
* 2023-09-08 (6d59b8c5): Merged PR 198: \[InProgress] Filtering Backend
* 2023-09-08 (58e3c963): Complete value page filters
* 2023-09-08 (8338e974): Merged PR 31: Sync
* 2023-09-08 (ea08977e): Merged PR 30: Deploy
* 2023-09-08 (e7b775c8): Merged PR 29: Delpoy
* 2023-09-08 (41593695): Resolve lint issues
* 2023-09-08 (d71b7524): updated get function
* 2023-09-08 (024f7348): created states and functions to store filter keyword in top level
* 2023-09-08 (f2fd284d): updated padding
* 2023-09-08 (2cf607f4): Merged PR 205: updated logic changes for ICPENormalized
* 2023-09-08 (46842660): updated logic changes for ICPENormalized
* 2023-09-08 (b4110fd0): Improve navigation
* 2023-09-08 (2221ef0f): Complete filters for impact
* 2023-09-08 (e353ad2f): resolved merge conflict
* 2023-09-08 (6f9703db): Merge branch 'develop' into PERF-116
* 2023-09-08 (5e7192aa): resolve conflicts
* 2023-09-08 (ff5eeb8d): updated for responsiveness
* 2023-09-08 (1724c28f): added functionality to pass filters from top level
* 2023-09-08 (f6e4df70): fixed
* 2023-09-08 (640737b6): Revert "Update IFD 2023 score"
* 2023-09-08 (20d22ef9): Merge branch 'PERF-105' into PERF-116
* 2023-09-08 (085459b9): Merged PR 200: Inform Risk Index on Home Page legend order change
* 2023-09-08 (5a045c88): Merged PR 201: Update IFD 2023 score
* 2023-09-08 (6740e0e1): Update IFD 2023 score
* 2023-09-08 (c49b167f): Inform Risk Index on Home Page legend order change
* 2023-09-08 (54b0e76e): Merged PR 197: fixed reverse issue in total ifd table
* 2023-09-08 (60bd0f5d): Merged PR 196: Change color of CO Capacity + Inform Risk Index
* 2023-09-08 (cdd08eb5): fixed reverse issue in total ifd table
* 2023-09-08 (f1f4362b): basic dropdown and filter done
* 2023-09-08 (c31f88fc): Change color of CO Capacity + Inform Risk Index
* 2023-09-08 (ff112e91): Remove comma
* 2023-09-08 (e97a17a3): Completed accountability
* 2023-09-08 (cae0c1a3): Merged PR 195: clickable home page cards changes
* 2023-09-08 (c6d84b97): empty function eslint fix for onCLick div event
* 2023-09-08 (f27b38cc): clickable home page cards changes
* 2023-09-08 (63a4915a): Add filters to audit page
* 2023-09-07 (7b77dd6a): Updated azure-pipelines-web.yml
* 2023-09-07 (8c5a7df9): Updated Web.tsx
* 2023-09-07 (dfe1fe25): Merged PR 28: Deploy
* 2023-09-07 (56500be9): Merge remote-tracking branch 'origin/staging' into develop
* 2023-09-07 (404d28fa): Merged PR 27: Deploy
* 2023-09-07 (86994f1d): Change logo
* 2023-09-07 (d52da512): Fix indent issue
* 2023-09-07 (5e482ca6): change icon location
* 2023-09-07 (3857c822): Updated Web.tsx
* 2023-09-07 (88fb93f4): Updated Web.tsx
* 2023-09-07 (0aa3c85d): Add basic template
* 2023-09-07 (57379e69): Merged PR 25: Deploy
* 2023-09-07 (382d1ede): Updated azure-pipelines\_filecopy.yml
* 2023-09-07 (c49f6708): Merged PR 23: Deploy
* 2023-09-07 (4e6413e0): Set up CI with Azure Pipelines
* 2023-09-07 (28d81226): Deleted azure-pipelines.yml
* 2023-09-07 (b18b1784): Set up CI with Azure Pipelines
* 2023-09-07 (07fa1d27): Merged PR 22: Deploy
* 2023-09-07 (aa507332): Deleted azure-pipelines-filecopy.yml
* 2023-09-07 (bf5ec3a7): Set up CI with Azure Pipelines
* 2023-09-07 (d814a90b): Deleted azure-pipelines-filecopy.yml
* 2023-09-07 (b22877ae): updated values page
* 2023-09-07 (2e4a9117): Merged PR 20: Latest
* 2023-09-07 (c62301de): Renamed azure-pipelines.yml to azure-pipelines-filecopy.yml
* 2023-09-07 (8dc93adb): Deleted azure-pipelines-filecopy.yml
* 2023-09-07 (f34f2433): Merged PR 19: Sync
* 2023-09-07 (eebb540e): Merged PR 18: Deploy
* 2023-09-07 (df7baa62): Set up CI with Azure Pipelines
* 2023-09-07 (b17fe61c): Merged PR 16: Sync
* 2023-09-07 (65cd53d4): Merged PR 15: Set up CI with Azure Pipelines
* 2023-09-07 (fe467661): updated Efficiency page
* 2023-09-07 (e6314816): Renamed azure-pipelines-filecopy-1.yml to azure-pipelines-filecopy.yml
* 2023-09-07 (e8e5f7d7): Deleted azure-pipelines-filecopy.yml
* 2023-09-07 (7208c8bb): Set up CI with Azure Pipelines
* 2023-09-07 (64580471): Merged PR 14: Sync
* 2023-09-07 (a8b7b175): Merged PR 13: File copy
* 2023-09-07 (b752e206): Updated azure-pipelines-filecopy.yml
* 2023-09-07 (78d5146c): Merged PR 12: Latest
* 2023-09-07 (d35b5528): updated impact page
* 2023-09-07 (5108687f): updated accountability page
* 2023-09-07 (1844bc5e): Renamed azure-pipelines.yml to azure-pipelines-filecopy.yml
* 2023-09-07 (d11a942d): Merged PR 190: Changes done
* 2023-09-07 (a89bb610): Merged PR 191: Change container name
* 2023-09-07 (9e9e134d): Change blob container
* 2023-09-07 (980e6118): Change container name
* 2023-09-07 (06c43323): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (08bed2aa): added title for description of Annual Survey on SH and SEA (March 2023)
* 2023-09-07 (bbf23208): Merged PR 189: merge files into dev
* 2023-09-07 (8b331b39): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (ec2e839d): Merged PR 188: merge dev into files
* 2023-09-07 (4fdd21b3): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (860f2563): changed Quantum Updates -> Quantum KPI Updates
* 2023-09-07 (569f7fed): Testing
* 2023-09-07 (eb5683c2): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (4ddc81ac): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (0f331469): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (7e038965): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (21a41d59): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (017a80c7): updated
* 2023-09-07 (7944c604): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (447b7a0c): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (ff0fe52f): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-07 (c49c581a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into url-btn
* 2023-09-06 (a96a20a5): Merged PR 11: sync
* 2023-09-06 (a062c6b9): Merged PR 10: s
* 2023-09-06 (c4f1de95): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-09-06 (fcc33884): Merged PR 8: Deploy
* 2023-09-06 (d083e7e9): Merged PR 9: Sync
* 2023-09-06 (5ae30674): Merged PR 7: Latest
* 2023-09-07 (8c19c777): Merge branch 'develop' into pl1
* 2023-09-06 (fbbf5a57): Rename icon
* 2023-09-06 (b4580351): Update Home Icon
* 2023-09-06 (6ffc4a51): Bug fix in the icon
* 2023-09-06 (8737a726): Add apple touch icon
* 2023-09-06 (7468cb73): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-06 (e3a8b653): add icon
* 2023-09-06 (c06968d8): Update fav
* 2023-09-06 (8bfdaf9f): add url btn
* 2023-09-06 (7124f23c): Add files
* 2023-09-06 (a70df93f): Merged PR 181: Change the blob storage
* 2023-09-06 (642971f8): Update azure-pipelines.yml for Azure Pipelines
* 2023-09-06 (b00c96c0): Remove console logs
* 2023-09-06 (5b3f0014): Resolve lint issues
* 2023-09-06 (1cda22ec): CHange blob container
* 2023-09-06 (b8d7dc0d): Merged PR 180: Refactor QA mapping
* 2023-09-06 (de12fe45): Merge branch 'BugFixes' into Improvements
* 2023-09-06 (d831dbaf): Refactor QA mapping
* 2023-09-06 (d2050ad3): Merge branch 'develop' into Improvements
* 2023-09-06 (92032b86): Add new structure
* 2023-09-06 (8e6bac7d): Merged PR 178: checked for data and adjusted the layout in greening page
* 2023-09-06 (96f929f6): updated
* 2023-09-06 (a7c0a920): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into fix-SEA-SH-graph-responsiveness
* 2023-09-06 (d05e31cb): increased line height in labels inside doughnut chart
* 2023-09-06 (7b4dcc78): checked for data and readjusted the layout
* 2023-09-06 (09ccafb4): Merged PR 176: fix-SEA-SH-graph-responsiveness and updated accountability page
* 2023-09-06 (a1669381): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into fix-SEA-SH-graph-responsiveness
* 2023-09-06 (4352faee): updated accountability page according to backend changes
* 2023-09-06 (9a85810a): fixed issue in SH and SEA graph
* 2023-09-06 (70a47321): Set up CI with Azure Pipelines
* 2023-09-06 (4e0af7c7): Merged PR 174: added mobile icon
* 2023-09-06 (73c735d8): Merged PR 173: Improve accountability
* 2023-09-06 (2374899f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into mobile-icon
* 2023-09-06 (80685193): added iconImageURL
* 2023-09-06 (6aaecf39): Improve accountability
* 2023-09-06 (f292f5eb): Merged PR 6: CICD
* 2023-09-06 (338e62d0): Merged PR 5: CICD change
* 2023-09-06 (fa8db4d4): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-09-06 (edc5c897): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-06 (99ad3867): Revert "Revert "Update UNDP urls""
* 2023-09-06 (5cc9f5a0): Revert "Update UNDP urls"
* 2023-09-06 (b7a30025): Update UNDP urls
* 2023-09-05 (b0df7b41): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-05 (b3dcdcb5): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-05 (6f50cf9d): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-05 (2cfb9fa3): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-05 (b25cd132): Merged PR 4: Sync
* 2023-09-05 (069cc806): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-09-05 (cde380e5): Merged PR 172: Deploy
* 2023-09-05 (e85b5710): Merged PR 171: added total carbon footprint per office and fixed some issues
* 2023-09-05 (21547409): fixed issues
* 2023-09-05 (cf124bf0): fixed issues
* 2023-09-05 (416b7fe8): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into total-carbon-footprint-per-office
* 2023-09-05 (7140af32): added basic graph for total-carbon-footprint-per-office
* 2023-09-05 (73646eda): Merged PR 170: Deploy
* 2023-09-05 (ded63851): Merged PR 169: FIxed the lint issues
* 2023-09-05 (d8529ab6): FIxed the lint issues
* 2023-09-05 (15de322a): Merged PR 168: Refactor "Carbon total fottprint per office" stat
* 2023-09-05 (f541cf19): Refactor "Carbon total fottprint per office" stat
* 2023-09-05 (5ec01206): Merged PR 167: total carbon footprint per bureau changes
* 2023-09-05 (d26a656c): total carbon footprint per bureau changes
* 2023-09-05 (05142fbc): Merged PR 166: Deploy
* 2023-09-05 (0fd16f26): Merged PR 164: Emission by Category changes
* 2023-09-05 (aa5b46fd): Merged PR 165: removed greening moonshots title
* 2023-09-05 (d808d873): added addComSep function
* 2023-09-05 (dc20132e): removed greening moonshots title
* 2023-09-05 (cf2eff23): greening card changes
* 2023-09-05 (375989b6): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-109-changes
* 2023-09-05 (80790272): emission by category graph changes
* 2023-09-05 (b7ec7582): Merged PR 163: added sorting for Latest Country Office Performance Audit Rating table
* 2023-09-05 (db711c76): added sorting for Latest Country Office Performance Audit Rating table
* 2023-09-05 (49c4cd5d): Merged PR 162: Added sorting to table columns that needed sorting, fixed sorting issue and refactored the code
* 2023-09-05 (eb14cf5a): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into fix-typo
* 2023-09-05 (642865f3): made the columns that need sorting sortable and refactored
* 2023-09-05 (f5def802): Merged PR 161: Add total and background color
* 2023-09-05 (43069358): Add total and background color
* 2023-09-05 (4f372461): Emission chart card changes
* 2023-09-04 (774dc018): Merged PR 160: Remove console logs
* 2023-09-04 (e339d693): Correct the year in trend line
* 2023-09-04 (e6c14b33): Merged PR 159: fixed typo
* 2023-09-04 (8d2fa071): fixed typo
* 2023-09-04 (fc69414e): Merge branch 'develop' into Improvements
* 2023-09-04 (92ca1665): Remove unwanted console logs
* 2023-09-04 (000b2852): Merged PR 158: made FE more fault tolerant and refactored code
* 2023-09-04 (71e32eb4): Merged PR 157: Improve testing
* 2023-09-04 (ff84405c): Add three indicators of value page
* 2023-09-04 (36f23b37): resolved merge conflict
* 2023-09-04 (067765a6): removed unnecessary console.log
* 2023-09-04 (9fc9234c): removed unnecessary console.logs or commented them
* 2023-09-04 (8eeaf6f6): made pages Efficiency, AccumulateDelivery, People, Greening, Values defensive and refactored some code
* 2023-09-04 (f11594e8): made pages defensive and refactored
* 2023-09-04 (3a7e59ad): updated
* 2023-09-04 (f2ef27a1): made teh IRRFPage defensive
* 2023-09-04 (ea071901): made the ImpactPage defensive
* 2023-09-04 (2411b878): Merge branch 'develop' into Improvements
* 2023-09-04 (90ed8b89): Add impact and accountability stats
* 2023-09-04 (86e5c5d5): Merged PR 156: text changes in impact section
* 2023-09-04 (83f1d501): text changes in impact section
* 2023-09-04 (f7cfde3f): created a function to check for non empty objects
* 2023-09-01 (b51420be): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-09-01 (a93e0357): add single indicator color
* 2023-09-01 (a2c3d75d): Merged PR 155: Deploy
* 2023-09-01 (f4b9e992): Merged PR 153: Resolve lint issue
* 2023-09-01 (b794ddd9): Merged PR 154: Fixed the horizontal chart width issues
* 2023-09-01 (e42e9aba): Fixed the horizontal chart width issues
* 2023-09-01 (aa9cfc6c): Resolve lint issue
* 2023-09-01 (03b3073e): Merged PR 152: Refactor testing
* 2023-09-01 (358ab544): Refactor testing
* 2023-09-01 (671def7d): Merged PR 151: Deploy
* 2023-09-01 (868f2f77): Merged PR 150: setup time durations in titles dynamically
* 2023-09-01 (4f619b85): resolved merge conflict
* 2023-09-01 (85a75d7e): fixed undefined issue
* 2023-09-01 (3c2f9966): showing time durations for titles dynamically done
* 2023-09-01 (6e2ebbc4): Merged PR 149: Deploy
* 2023-09-01 (de3cbf23): Merged PR 148: mobile responsive changes
* 2023-09-01 (ad74c3c6): mobile responsive changes
* 2023-09-01 (3d03bab6): Merged PR 147: Add "vacancy rate" score
* 2023-09-01 (68323366): Merge branch 'develop' into Improvements
* 2023-09-01 (78e028c7): Refactor testing
* 2023-09-01 (dac0c8c5): Merged PR 146: Deploy
* 2023-09-01 (c1f36af3): Merged PR 145: fixed issues in QA completion graph and ifd graph and showing indicator score for Engagement Historical trend in people page
* 2023-09-01 (f03931d0): updated
* 2023-09-01 (5adf6f61): updated data string
* 2023-09-01 (088e2156): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into ifd-scores-table-update
* 2023-09-01 (e74ece96): set the indicator score for people page historical trend
* 2023-09-01 (c7f84437): fixed isses in QA completion graph and fixed issue in data getting reset to original order in IFD scores
* 2023-09-01 (9d386f57): Merged PR 142: Add "Engagement Historical Trend" statisctic score
* 2023-09-01 (8c8142ad): Add "Engagement Historical Trend" statisctic score
* 2023-09-01 (76026b0b): Merged PR 141: Add time range for required stats
* 2023-09-01 (adef277a): Resolve lint issues
* 2023-09-01 (12ae269e): Add time ranges
* 2023-09-01 (95f29afe): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into ifd-scores-table-update
* 2023-09-01 (4a5799f2): moved strings to en-us.js and fixed issues in QA completion graph
* 2023-09-01 (01a51f91): Merged PR 140: setting up the title of ifd scores dynamically - temp fix
* 2023-09-01 (9c3c36cb): Merged PR 139: Deploy
* 2023-09-01 (92801e09): Merged PR 138: table graph custom legend changes
* 2023-09-01 (b4f8a3fe): table graph custom legend changes
* 2023-09-01 (3940bf1e): Merged PR 137: TableGraphCardProps changes
* 2023-09-01 (7a3e3d5b): TableGraphCardProps changes
* 2023-09-01 (cce512ad): setting up the title of ifd scores dynamically
* 2023-09-01 (0403b61d): Merged PR 133: Deploy
* 2023-09-01 (88eba2f3): Merged PR 136: Resolve lint issue
* 2023-09-01 (0b134e00): Resolve lint issue
* 2023-09-01 (586df33d): Merged PR 135: Refactor file reading
* 2023-09-01 (c18496b2): Merge branch 'develop' into PRF-66new
* 2023-09-01 (896ea6d3): Refactor file reading
* 2023-09-01 (475d1064): Merged PR 134: Commit c1154041: fixed the legend alignment issue in maps
* 2023-09-01 (1a8fa87c): added cutom legend widgets for charts
* 2023-09-01 (5df7eeac): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-101-changes
* 2023-09-01 (d704671b): Merged PR 132: converted titles to Camel Case
* 2023-09-01 (df8da82d): fixed-typos

### August

* 2023-08-30 (a8d804e5): nav changes
* 2023-08-31 (93380525): Merged PR 131: Deploy
* 2023-08-31 (9ef69e97): Merged PR 130: Updated the color code issue in COCapacity matrix
* 2023-08-31 (4d9da415): Merged PR 129: updated sorting order
* 2023-08-31 (b3360b7d): Merged PR 128: updated and fixed more padding issues
* 2023-08-31 (5056f697): Merged PR 127: setting up the ifd scores dynamically
* 2023-08-31 (2cbf73b1): updated
* 2023-08-31 (1889c619): fixed issue in color codes in COCapacity map
* 2023-08-31 (6db26347): removed unncessary console.log
* 2023-08-31 (7a39f75d): updated sorting order
* 2023-08-31 (28696add): updated and fixed more padding issues
* 2023-08-31 (8ace4faf): updated
* 2023-08-31 (28e5d652): setting the total IFD data dynamically
* 2023-08-31 (08873012): Merged PR 126: deploy
* 2023-08-31 (0c145dfd): Merged PR 125: updated
* 2023-08-31 (83e7eb4e): updated
* 2023-08-31 (85ab7073): Merged PR 124: deploy
* 2023-08-31 (85ae279b): Merged PR 123: removed rank column in Proportion of Positive Audit Rating Results by Bureau...
* 2023-08-31 (ab1c109c): removed rank column in Proportion of Positive Audit Rating Results by Bureau and updated renderColumn
* 2023-08-31 (c1154041): fixed the legend alignment issue in maps
* 2023-08-31 (673267f6): Merged PR 122: Deploy
* 2023-08-31 (7dfe171c): Merged PR 121: showing indicator scores
* 2023-08-31 (d4207a1c): removed unnecessary overflow-y in header
* 2023-08-31 (ad2b050f): showing indicator scores for impact page and accountability page
* 2023-08-31 (50eccef9): created IndicatorScoreContext and saved the indicatorScoreson the context
* 2023-08-31 (140e6d3e): Merged PR 120: Deploy
* 2023-08-31 (e025a68c): Merged PR 119: Commit 939aacf5: text and title changes in people section and home page
* 2023-08-31 (98dbec7e): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-104-changes
* 2023-08-31 (939aacf5): text and title changes in people section and home page
* 2023-08-31 (56965c8e): Merged PR 118: deploy
* 2023-08-31 (bf3635c6): Merged PR 117: text on info cards padding on sides increased to 20px
* 2023-08-31 (8a1309ef): resolved merge conflict
* 2023-08-31 (048c999a): deleted unnecessary textcard component
* 2023-08-31 (565097d2): made the sides of text info boxes 20px
* 2023-08-31 (8ffa9185): created dummy data and analysis on bureau done
* 2023-08-30 (3fef1b5d): Fix IRRF sort
* 2023-08-30 (e83e836c): Merged PR 116: IRRF fix
* 2023-08-30 (7270194d): IRRF fix
* 2023-08-30 (9475474e): Merged PR 115: deploy
* 2023-08-30 (34fd9f79): Fix sorting issues
* 2023-08-30 (7f78eb40): add perc num
* 2023-08-30 (94839b63): add new perc
* 2023-08-30 (abc1212f): Merged PR 114: deploy
* 2023-08-30 (8ec794d9): Fix responsive issues
* 2023-08-30 (e503c566): Fix responsive
* 2023-08-29 (b0c059b4): Merged PR 113: fix build issue
* 2023-08-29 (4eb28eb8): fix build issue
* 2023-08-29 (f8abe990): Merged PR 112: Fix score issue
* 2023-08-29 (70df31e2): Fix score issue
* 2023-08-29 (808d56a8): Merged PR 111: Deploy
* 2023-08-29 (48a6113a): Merged PR 110: FIxed the semicolon eslint issue
* 2023-08-29 (435b3d1f): FIxed the semicolon eslint issue
* 2023-08-29 (117f5046): Merged PR 109: Sync
* 2023-08-29 (2dc338b0): Merged PR 108: loading changes for pages
* 2023-08-29 (4830b738): loading changes for pages
* 2023-08-29 (524426a7): Merged PR 107: Cheange xlsx file to csv
* 2023-08-29 (8d188658): add new stats
* 2023-08-29 (94b36fee): Resolve ifd issue
* 2023-08-29 (83664d28): Merge branch 'develop' into PRF-66new
* 2023-08-29 (03fa0666): resolve lint issues
* 2023-08-29 (981cfc29): Chenage from excel to csv
* 2023-08-29 (4bc5b352): Merged PR 106: Sync
* 2023-08-29 (0c9dda93): Merged PR 105: fixed issue and reversed data on ifd scores graph
* 2023-08-29 (c8be1bcf): Merged PR 103: fixed issue in audit page
* 2023-08-29 (4b1574ad): fixed issue and reversed data on ifd scores graph
* 2023-08-29 (895a4726): Merged PR 104: Removed indicator score
* 2023-08-29 (a39e9a05): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into add-indicator-score
* 2023-08-29 (c0b0ac8f): updated
* 2023-08-29 (69c534d5): fixed issue in audit page
* 2023-08-29 (2269924d): Merged PR 102: Sync
* 2023-08-29 (92ef843e): Update web cicd
* 2023-08-29 (ae96df24): Merged PR 101: home page Country Office Capacity Matrix map component changes
* 2023-08-29 (ca27d44a): Merged PR 100: getting data from BE for total IFD scores
* 2023-08-29 (33875b4f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-96-changes
* 2023-08-29 (f455fad1): home page Country Office Capacity Matrix map component changes
* 2023-08-29 (56288c58): updated
* 2023-08-29 (c35296f4): getting data from backend for total ifd scores
* 2023-08-29 (6bcf4144): Merged PR 99: updated the style
* 2023-08-29 (fbe3a97c): updated the style
* 2023-08-29 (2c7e360c): Merged PR 98: added indicator scores to the data cards
* 2023-08-29 (f6bdb9f1): updated
* 2023-08-29 (4e4671fc): added indicator score to the data cards
* 2023-08-29 (e0707ede): Merged PR 97: Add nav stats(Impact and Accountability)
* 2023-08-29 (8ce09696): Add nav stats
* 2023-08-28 (3eb96da2): Merged PR 95: Change title Co
* 2023-08-28 (33dd465c): Change title Co
* 2023-08-28 (ab2c59b6): Merged PR 3: Sync
* 2023-08-28 (bb83bddd): Merged PR 94: Remove %
* 2023-08-28 (7a59c4b7): Remove %
* 2023-08-28 (8a86ea9a): Merged PR 93: Latest
* 2023-08-28 (3cd872ea): Merged PR 92: generating colors for each stat seperately based on the values
* 2023-08-28 (17fa14c1): generating colors for each stat seperately based on the values
* 2023-08-28 (f2d1250f): Merged PR 91: change column indexes
* 2023-08-28 (deb2756b): change column indexes
* 2023-08-28 (f65d93d4): Merged PR 90: Deploy
* 2023-08-28 (c7e31666): Merged PR 89: removed gender distribution by bureau and added gender distribution by position
* 2023-08-28 (a6aa4776): removed gender distribution by bureau and added gender distribution by position on people page
* 2023-08-28 (d8045ec1): Merged PR 87: change filename
* 2023-08-28 (781ae290): Merged PR 88: Deploy
* 2023-08-28 (9304fc38): change filename
* 2023-08-28 (f73b0435): Merged PR 86: changed the graph order and resolved merge conflicts
* 2023-08-28 (a07b4c61): updated
* 2023-08-28 (b12c096f): resolved merge conflict
* 2023-08-28 (f6395a2a): changed the graph order
* 2023-08-28 (4368372e): Merged PR 84: Sync
* 2023-08-28 (47580ace): Merged PR 83: changes in card titles
* 2023-08-28 (603f369f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into perf-92-changes
* 2023-08-28 (89c6133c): changes in card titles
* 2023-08-28 (44ddd6f6): Merged PR 82: added title for the total emmissions by year trend line graph
* 2023-08-28 (e97359c7): fixed merge conflict
* 2023-08-28 (25b478eb): Merged PR 81: title and info changes for cards
* 2023-08-28 (7ed45552): added title for the total emmissions by year trend line graph
* 2023-08-28 (68417c6f): title and info changes for cards
* 2023-08-28 (ed137b9c): Merged PR 80: Deploy FE
* 2023-08-28 (6774bde8): Merged PR 79: made the changes in the homepage
* 2023-08-28 (e4af43ea): made the changes in the homepage
* 2023-08-28 (5827fd92): Merged PR 78: Getting nav stats from backend
* 2023-08-28 (abe895ce): updated
* 2023-08-28 (1d49604a): removed some unnecessary console.logs and fixed the undefined error on the homepage
* 2023-08-28 (333d2fd8): removed unnecessary console.log
* 2023-08-28 (ed6a0019): Homepage score calculating from the data getting from backend
* 2023-08-28 (1cc06524): Merged PR 76: updated title
* 2023-08-28 (c2ca75b9): Merged PR 77: Add qa completion handler
* 2023-08-28 (cdbd8f5e): Resolve lint issues
* 2023-08-28 (9fb5ee37): Merge branch 'develop' into PRF-66new
* 2023-08-28 (d72981f7): Add basic structure
* 2023-08-28 (1e83649c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into institutional-revenue-actuals-and-targets
* 2023-08-28 (27bf7117): updated title
* 2023-08-28 (790a6972): getting data from backend
* 2023-08-25 (c44fe934): Merged PR 75: Sync
* 2023-08-25 (910b3a87): Merged PR 74: institutional-revenue-graph
* 2023-08-25 (9728b070): connected with the backend
* 2023-08-25 (6ebc13bc): Merged PR 73: Change billion to miliion
* 2023-08-25 (2e34420b): Change billion to miliion
* 2023-08-25 (3d124cf8): Merged PR 71: updated
* 2023-08-25 (f223ae78): Merged PR 72: Add nav stats
* 2023-08-25 (313b8ba1): Add nav stats
* 2023-08-25 (aa710e42): updated
* 2023-08-25 (012033be): basic graph for institutional revenue target done
* 2023-08-25 (cbd4610f): Merged PR 70: Add Monthly rev stat
* 2023-08-25 (f343b9e8): Add Monthly rev stat
* 2023-08-24 (366e236a): drop 2018
* 2023-08-24 (bab0fa9f): drop 2018
* 2023-08-24 (4424541d): remove 2018
* 2023-08-24 (581eae00): drop 2018
* 2023-08-24 (f29833c7): Merged PR 69: Deploy
* 2023-08-24 (b74b2604): Merged PR 68: QA Completion graph done
* 2023-08-24 (c724395c): connected with the backend
* 2023-08-24 (834116df): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into QA-Completion-graph
* 2023-08-24 (b50b0b6f): QACompletion basic graph done
* 2023-08-24 (82e6decb): Merged PR 67: Add "AUDIT\_QA\_COMPLETION" stat
* 2023-08-24 (aa61f41c): Add test cases
* 2023-08-24 (2094a13a): Resolve lint issues
* 2023-08-24 (11311bcf): Add "AUDIT\_QA\_COMPLETION" stat
* 2023-08-24 (c1fabac2): Merged PR 66: Deploy
* 2023-08-24 (bee222dd): Merged PR 63: moved trend line CO2 emissions to values page
* 2023-08-24 (db2f2a7e): Merged PR 65: merge dev into stage
* 2023-08-24 (f191ea16): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-24 (50c0284a): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (c8ddaae5): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-24 (2eb96ed7): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (bbd8c33c): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-24 (d3cb405e): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-24 (ec893d7b): Merged PR 64: Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (58e9f109): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (88cf0c65): moved trend line CO2 emissions to values page
* 2023-08-24 (a4e797e9): Merged PR 62: Merge dev into staging
* 2023-08-24 (51adb9d0): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-24 (71b054ed): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (aa02cc42): Merged PR 61: Merge dev into staging
* 2023-08-24 (94bdd3c0): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (01b038bf): Merged PR 58: fixed issues in "Annual Survey on SH and SEA (March 2023)" chart and "UNDP’s Aid Transparency Rank and Score" chart
* 2023-08-24 (907a05e8): Merged PR 59: Resolve issue in "EFFICIENCY\_TOT\_CONTRIBUTIONS" stat
* 2023-08-24 (0d196e2d): Merged PR 60: changed the title of Co performance graph
* 2023-08-24 (5ca20e4f): Change CDN
* 2023-08-24 (9995565c): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (d62e98b4): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (6332ea9f): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (77d6793b): changed the title of Co performance graph
* 2023-08-24 (2f9375af): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (0021cc88): Rename vacancy file and change the blob triger container
* 2023-08-24 (7a286ac2): Remove console log
* 2023-08-24 (1117f333): Resolve issue in the "EFFICIENCY\_TOT\_CONTRIBUTIONS" stat
* 2023-08-24 (32540712): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (937500dc): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (8cdf23c1): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (32444cc6): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (191f846a): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (8f27a1bb): added the x-axis values, fixed typo
* 2023-08-24 (8753a7d7): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (6063b336): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (c0f2da67): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (6894c7e8): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (5bcc2a7f): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-24 (fc274ec2): added % mark for values in y-axis
* 2023-08-24 (461e1c98): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-16 (41639486): deploy changes
* 2023-08-23 (b8550e7d): rounding
* 2023-08-23 (b64ae1ac): round stats
* 2023-08-23 (c21dd480): Merged PR 56: Country Office Capacity Matrix done
* 2023-08-23 (5177d91d): resolved the merge conflict
* 2023-08-23 (8d382649): county office capacity matrix done
* 2023-08-23 (7dbfaf9d): add home key stats
* 2023-08-23 (6de6d1c0): Merged PR 55: Created chart for latest country audit rating and fixed some issues in the map
* 2023-08-23 (55614e2f): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into home-page-development
* 2023-08-23 (62ed49de): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (4fccb684): fixed some issues in the map
* 2023-08-23 (108887ea): extracted strings in Accountability page to mystring.d.ts
* 2023-08-23 (10d6c4c1): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (a6d3563e): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (b4ed725f): Latest Country Office Performance Audit Rating done
* 2023-08-23 (698b94ae): Merged PR 49: Add blob trigger function
* 2023-08-23 (37025be2): Add testing
* 2023-08-23 (af2bddec): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (1e1077f8): Merged PR 54: Resolve lint issues
* 2023-08-23 (b5b7a137): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (92bd6dd8): Resolve lint issues
* 2023-08-23 (99a25a33): Add key stats
* 2023-08-23 (7c873c19): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (03343710): resolved merge conflict
* 2023-08-23 (7ea81c05): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (5765c2b8): Merged PR 52: Add summery in detailed
* 2023-08-23 (e39be5c6): remove hard coded values
* 2023-08-23 (32960de1): Merged PR 53: created new card for charts
* 2023-08-23 (2cc63059): adjusted the width of the datacard cols
* 2023-08-23 (4c0ba6fb): Update total array
* 2023-08-23 (164792cc): migrated charts to datacard
* 2023-08-23 (090ab2b0): moved the charts to data card and fixed some alignement issues in data card
* 2023-08-23 (b78e3375): basic updated data card done
* 2023-08-23 (bd66471c): Merge branch 'develop' into BugFixes
* 2023-08-23 (a94c53da): Add home key stats
* 2023-08-23 (0681c56e): Add key stats
* 2023-08-23 (a465205b): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (55d3a212): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (7417425f): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-23 (8636cce0): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (908c273b): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (8eec2ccb): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (43eaa21b): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (13a9f47b): update server CICD
* 2023-08-22 (c739e335): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (c71d0d1e): Merge branch 'develop' into BugFixes
* 2023-08-22 (f41a280d): Add summery in detail
* 2023-08-22 (87a4cb81): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (1fb4aa34): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (165a22e3): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-22 (8e26ea5b): updated
* 2023-08-22 (c21d8522): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-22 (d57c5124): Merged PR 51: Add summery data
* 2023-08-22 (c3300687): Add summerydata
* 2023-08-22 (74e11555): irrfhandler completed
* 2023-08-22 (a594aa00): Merged PR 50: Resolve duplicate issue
* 2023-08-22 (e927127a): Resolve duplicate issue
* 2023-08-22 (cb609579): ADD handlers
* 2023-08-22 (3fe9d0cc): Fix UI issues
* 2023-08-22 (4ccc6694): made the component for INFORM+Country Office Capacity Matrix
* 2023-08-22 (18ad0820): Add blob triger
* 2023-08-22 (f7352f50): Merge branch 'develop' into file-processor
* 2023-08-21 (c3cd8427): Merged PR 48: Add "AUDIT\_LATEST\_RATING" stat
* 2023-08-21 (6cf4d9a1): Rename response array name
* 2023-08-21 (9d9a14a1): Add "AUDIT\_LATEST\_RATING" stat
* 2023-08-21 (66243aba): hide desc for gender
* 2023-08-21 (32c3312e): Fix minor UI changes
* 2023-08-21 (34e0f230): Fix next week change
* 2023-08-21 (b831f595): Merged PR 46: color changing based on the value of the global score
* 2023-08-21 (a8cb731c): Merged PR 47: Add "HOME\_CAPACITY\_MATRIX" stat
* 2023-08-21 (384335b0): Add "HOME\_CAPACITY\_MATRIX" stat
* 2023-08-21 (64beb494): color changing based on the value of the global score
* 2023-08-21 (634cbad7): Merged PR 45: changes
* 2023-08-21 (80408d55): changed the scrollable behaviour
* 2023-08-21 (ae5edf8e): rounded off the scores in header and greeting score calculating from the header scores
* 2023-08-21 (8cd83e03): Merged PR 44: added the graph for total emissions by year trend line
* 2023-08-21 (0ec99f2c): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-21 (66d5ee92): moved the strings of trend line graph to mystrings.d.ts
* 2023-08-21 (efd1359a): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-21 (095c1589): added basic total emissions by year with trend line
* 2023-08-21 (262fd73b): Merged PR 43: Rename the stattype name
* 2023-08-21 (dca8421c): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-21 (dcd5f236): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (10e3102a): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (cdb1077c): Rename the stattype name
* 2023-08-21 (a18da202): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-21 (cb74faba): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (69685336): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into value-page-development
* 2023-08-21 (4a811953): Merged PR 41: Add "efficiency total" stat
* 2023-08-21 (f9d2e0ee): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-21 (3feec87a): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (47d86d52): Merged PR 42: updated the links
* 2023-08-21 (95a804c4): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (e50ccd70): updated the links
* 2023-08-21 (a42e374c): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (aaad6c44): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-21 (88752384): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-21 (b845dd68): Add "efficiency total" stat
* 2023-08-18 (5c84f603): Merged PR 40: Resolve bug in array
* 2023-08-18 (4b9eb029): Resolve bug in array
* 2023-08-18 (977fa570): Merged PR 39: getting data from the backend for total contribution vs targets by year
* 2023-08-18 (ce49bb09): getting data from the backend for total contribution vs targets by year
* 2023-08-18 (ad27b6e9): Merged PR 38: Resolve value array issue
* 2023-08-18 (a509cc7b): Resolve value array issue
* 2023-08-18 (1a1fcc44): Merged PR 37: Update efficiency issue
* 2023-08-18 (7dc8155e): Update naming
* 2023-08-18 (cdae35ef): Update efficiency issue
* 2023-08-18 (1b8aa279): Merged PR 36: updated
* 2023-08-18 (9f925fdb): updated
* 2023-08-18 (40a8f172): updated
* 2023-08-18 (ae36c8e0): Merged PR 35: updated
* 2023-08-18 (6c650a4b): updated title
* 2023-08-18 (7144e2bd): updated
* 2023-08-18 (6a3d5d67): updated the string
* 2023-08-18 (16b79f1f): Merged PR 31: header made to show values and change color of the value based on the value
* 2023-08-18 (a67f9933): Merged PR 32: frontend for total Contributions vs Targets by year done
* 2023-08-18 (d712b8c6): Merged PR 34: resolve lint issues
* 2023-08-18 (bdff6914): resolve lint issues
* 2023-08-18 (28e4a1d7): basic
* 2023-08-18 (ec3f2238): Merged PR 33: Add "Total Contributions vs Targets by Year" stat
* 2023-08-18 (13296448): Add "Total Contributions vs Targets by Year" stat
* 2023-08-18 (fa7f15c8): frontend for total Contributions vs Targets by year done
* 2023-08-18 (f940cd6a): header made to show values and change color of the value based on the value
* 2023-08-18 (1689aaf4): add template
* 2023-08-18 (60fdbca6): Merged PR 30: getting the avg from the backend and improve the styling of the dash line
* 2023-08-18 (d6b4be78): updated the dash line styles
* 2023-08-18 (ad93bd50): Merged PR 29: Changes on the title of Total Delivery vs Total targets and updated Just for you section links
* 2023-08-18 (b3e4138c): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into current-vacancy-rate-by-bureau
* 2023-08-18 (3b96b7af): getting the avg for the people vacancy rate from the backend done
* 2023-08-18 (9f7129f6): updated Just for You section and moved the data to .ts file from .json file
* 2023-08-18 (6e5f803f): Merged PR 28: Add average value to "PEOPLE\_VACANCY\_RATE" stat
* 2023-08-18 (8ea04772): updated the title of the total deliveries vs total targets
* 2023-08-18 (5a7e6224): Merge branch 'develop' into PERF-29
* 2023-08-18 (4fe6ec9f): Add average value to "PEOPLE\_VACANCY\_RATE" stat
* 2023-08-18 (e3365c03): avg calc
* 2023-08-17 (d6f2bdae): Merged PR 27: Change calculation in vacancy rate
* 2023-08-17 (f9637293): Change calculation
* 2023-08-17 (f8d4464c): Merged PR 26: basic graph done
* 2023-08-17 (e5ec1475): basic graph done
* 2023-08-17 (89cc5e55): Merged PR 25: updated title and map zoom levels, height
* 2023-08-17 (0c12f1b4): updated title and map zoom levels, height
* 2023-08-17 (0eee4d18): Merged PR 24: Removed the bottom legend desc of the total deliveries vs targets
* 2023-08-17 (b4b22765): removed unused imports
* 2023-08-17 (513d1144): removed the legend of the total deliveries vs targets table
* 2023-08-17 (e9083e47): Merged PR 22: added total deliveries vs targets in the efficiency page
* 2023-08-17 (06133740): Merged PR 23: fixed paddings issue
* 2023-08-17 (501e3daf): fixed paddings issue
* 2023-08-17 (841bd795): Added total deliveries vs targets per yr in the efficiency page
* 2023-08-17 (17f484bf): removed unnecessary comments
* 2023-08-17 (7d75dab8): Merged PR 21: total deliveries vs total target graph and commented out the QA SESP graph
* 2023-08-17 (310f4162): commented out the QA and SESP completion rates graph for now
* 2023-08-17 (5c85d1eb): Total deliveries vs Targets per year done
* 2023-08-17 (73481fd1): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-17 (fe36698a): Merged PR 20: Add "EFFICIENCY\_TOT\_DEL\_TARGET" stat
* 2023-08-17 (98c3d6b4): Resolve lint issues
* 2023-08-17 (5e4652c2): Add "EFFICIENCY\_TOT\_DEL\_TARGET" stat
* 2023-08-16 (98e6d1f0): Merged PR 19: Update to one decimal place
* 2023-08-16 (f68b857c): Update to one decimal place
* 2023-08-16 (f62c87c4): Merged PR 18: fixed issue in getting undefined for icpRatingScore
* 2023-08-16 (2b0d9c6d): fixed issue in getting undefined in icpRatingScore
* 2023-08-15 (01ff98aa): Merged PR 17: Number of countries in each area based on total ifd scores done
* 2023-08-15 (588e56e5): Number of countries in each area based on total ifd scores done
* 2023-08-15 (c091bbe2): Merged PR 16: updated chart heights
* 2023-08-15 (2d94b3df): updated chart heights
* 2023-08-15 (657bcc6b): Merged PR 15: Position Management by Bureau
* 2023-08-15 (196e429f): removed unncessary dummydata
* 2023-08-15 (bd2a3bb2): fixed issue in getting data in loop
* 2023-08-15 (159f7430): added scale labels
* 2023-08-15 (1725edb8): Merged PR 14: Resolve response issue
* 2023-08-15 (e08b53a9): Merge branch 'develop' into PERF-60
* 2023-08-15 (15f461b1): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into people-page-development
* 2023-08-15 (d097535a): Resolve response issue
* 2023-08-15 (0a26926a): Merged PR 13: fixed styling of data labels in for QA completion page
* 2023-08-15 (6cc1f5ed): fixed styling of datalabels in for QA completion page
* 2023-08-15 (2e6bb59f): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-15 (710f6cd3): Position management by bureau chart hardcoded done
* 2023-08-15 (26d523a0): Merged PR 12: Add " Average ICPE Rating Score for 2022" stat
* 2023-08-15 (b0f61d2a): Merge branch 'develop' into PERF-60
* 2023-08-15 (8a6719e4): Fix naming issue
* 2023-08-15 (10a155e9): Update "people mapper" stat data structure
* 2023-08-15 (48933c79): Add " Average ICPE Rating Score for 2022" stat
* 2023-08-15 (ad57b9c0): Merged PR 11: Moonshots graph created for Impact page
* 2023-08-15 (7ab8f539): resolved merge conflict
* 2023-08-15 (11cac0a3): Add new graphs to accountability
* 2023-08-15 (74c9ba38): Combine chart
* 2023-08-15 (b783f310): fixed typo
* 2023-08-15 (9e84f618): added legend and fixed some layout issues
* 2023-08-15 (8cb6948c): refactored and restructured, added moonshots to tablegraph and renamed moonshotgraph -> progressbar
* 2023-08-15 (db25e524): resolved merge conflict
* 2023-08-15 (11a50b01): basic Moonshots graph done
* 2023-08-15 (b4ca626a): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-15 (78807fc6): Deleted azure-pipelines.yml
* 2023-08-15 (86afd48d): Merged PR 10: Position Management by Bureau
* 2023-08-15 (a7336674): Merge branch 'develop' into Perf-29
* 2023-08-15 (25af8953): Add "PEOPLE\_POSITION\_MANAGE" stat
* 2023-08-14 (b317dc39): Add bar chart and navigation
* 2023-08-14 (7d63840f): Revert "Revert "Remove sidemenu""
* 2023-08-14 (5cf0b90f): Revert "Remove sidemenu"
* 2023-08-14 (ef88e0af): Merged PR 9: Update the data array
* 2023-08-14 (e79575be): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-14 (e7018a45): Update the data array
* 2023-08-14 (3947c6b6): Merged PR 8: Complete the peoples page "Current Vacancy Rate by Bureau" stat
* 2023-08-14 (088ed97a): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-14 (e6d405db): Resolve lint issues
* 2023-08-14 (91919d5b): Complete the people endpoint
* 2023-08-13 (180980dd): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-13 (1b030cde): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-13 (c5a10272): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-13 (5ea736d0): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-13 (230604db): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-13 (8a58745e): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-13 (f7065523): Set up CI with Azure Pipelines
* 2023-08-13 (6a6cf9af): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-13 (a0523ee7): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-13 (020d9ded): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-11 (155fd841): Remove sidemenu
* 2023-08-11 (a5fab99a): Merged PR 7: Fixed issues in engagement historical trend
* 2023-08-11 (935ef941): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (f7966255): fixed issues in layout
* 2023-08-11 (befc90ef): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (332ffd62): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into people-page-development
* 2023-08-11 (6f0f7cb2): fixed issues in Engagement Historical Trend
* 2023-08-11 (b25080df): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (4fe4e230): Add basic structure
* 2023-08-11 (c2870b0b): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (78b5dc39): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (0dec80e6): Merged PR 6: fixed issues in statcards and typos in just for you section
* 2023-08-11 (a1317f4a): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (f8e8efcb): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into fix-issues-in-homepage
* 2023-08-11 (c21a0ce0): Merged PR 5: Add stat type
* 2023-08-11 (c2a749a9): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (0332378d): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (d92f5285): fixed issues in statcards in homepage
* 2023-08-11 (97a8b82a): Add stat type
* 2023-08-11 (ea2f63bb): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (6c88da35): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (3ab4ef96): Merged PR 3: People Page Development - Engagement Historical Trend
* 2023-08-11 (ae95478f): resolved merge conflict
* 2023-08-11 (34f105c2): Fix Audit reopen
* 2023-08-11 (7a1d4b1b): Fix font load issue
* 2023-08-11 (1ea8b928): Remove proxima nova for all fonts
* 2023-08-11 (a430aa19): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (2618b9c4): Merge branch 'develop' of https://dev.azure.com/xeptagon/performance-app/\_git/performance-app into people-page-development
* 2023-08-11 (b6e677ac): updated x axis of engagement historical trend
* 2023-08-11 (e9348402): added strings
* 2023-08-11 (b442b79c): made tooltip posistion more responsive
* 2023-08-11 (546e8762): added basic engagement historical trend
* 2023-08-11 (e938afc2): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (c34f3219): Merged PR 2: Add AUDIT\_RATING stat
* 2023-08-11 (07770e34): Add AUDIT\_RATING stat
* 2023-08-11 (ee686519): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (c32e7126): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (b6dd4168): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (372f5128): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (43e5f071): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (ee1ad354): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (a7b3bb12): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-11 (63b6f4b4): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (02942391): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (9482f3de): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (207d1676): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (c42ec74c): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (2353c4f9): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (c8171de8): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (958dc075): Update azure-pipelines-server.yml for Azure Pipelines
* 2023-08-10 (b4a9aa21): Merged PR 1: sync
* 2023-08-10 (c1028292): Merge pull request #41 from xeptagondev/fonts
* 2023-08-10 (b1e4f560): Merge pull request #40 from xeptagondev/charts-not-responsive
* 2023-08-10 (5f7180ea): Fix font issue
* 2023-08-10 (fd1a7039): fixed issue in charts not responsive
* 2023-08-10 (6562eacc): font change
* 2023-08-09 (504855c6): Revert "Revert "Add custom font""
* 2023-08-10 (bd9189c2): fixed issues in responsiveness in Audit/Country Office Audit
* 2023-08-10 (7199aae7): Updated sp-deploy.ps1
* 2023-08-10 (feac2f90): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-10 (0c1ba3cd): basic line chart to show engagement historical trend done
* 2023-08-10 (712e6081): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-10 (627f29a3): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-09 (05fcd171): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-09 (92fd66cb): Updated sp-deploy.ps1
* 2023-08-09 (3766b90e): Merge pull request #39 from xeptagondev/people-page-development
* 2023-08-09 (6545f900): updated
* 2023-08-09 (11604cc3): Merge pull request #38 from xeptagondev/people-page-development
* 2023-08-09 (20d0b66c): changed the label order in Gender Breakdown pie chart
* 2023-08-09 (091843c5): Merge pull request #37 from xeptagondev/people-page-development
* 2023-08-09 (aa81b3be): Merge branch 'develop' into people-page-development
* 2023-08-09 (4b0d71dc): Add sentence to legend
* 2023-08-09 (a1cc0a34): added gender distribution by position, added peoples page fixed responsiveness of graphs in peoples page
* 2023-08-09 (74792230): added gender distribution by position graph
* 2023-08-09 (867040d2): Reduce font size
* 2023-08-09 (0a69e0ab): Fix label issue on other charts
* 2023-08-09 (f288e304): Merge pull request #35 from xeptagondev/people-page-development
* 2023-08-09 (e4603315): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into people-page-development
* 2023-08-09 (4be3f79d): added labels for gender distribution by bureau section
* 2023-08-09 (5a092cf5): Merge pull request #36 from xeptagondev/PERF-14
* 2023-08-09 (9288c5d8): showing values in gender distribution by bureau percentages
* 2023-08-09 (10984e89): Update gtesting
* 2023-08-09 (b62ca69b): Remove extra stats
* 2023-08-09 (62b3e101): Merge pull request #33 from xeptagondev/PERF-14
* 2023-08-09 (6c093484): add labels to pie chart
* 2023-08-09 (b2e317a1): Resolve lint issues
* 2023-08-09 (a5a0b2a1): removed unnecessary width
* 2023-08-09 (d7b20cca): moved strings in people page to mystrings.d.ts
* 2023-08-09 (b87518c9): Gender Distribution by Bureau done
* 2023-08-09 (ab45d2c0): Add auditmapper new stats
* 2023-08-09 (8cc65ff2): Read from cln-files
* 2023-08-09 (7ae60b56): Revert "Add custom font"
* 2023-08-09 (d63a9319): updated
* 2023-08-09 (f5ca11c4): Add custom font
* 2023-08-09 (87902f85): Change audit mapper implementation
* 2023-08-09 (8a830f5c): Merge pull request #32 from xeptagondev/people-page-development
* 2023-08-09 (b2af6c66): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into people-page-development
* 2023-08-09 (c410e567): added gender breakdown graph
* 2023-08-08 (6515e020): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-08 (bc16e4ab): Renamed sp-deploy to sp-deploy.ps1
* 2023-08-08 (6528a175): Update azure-pipelines-web.yml for Azure Pipelines
* 2023-08-08 (46e00417): Added sp-deploy
* 2023-08-08 (4dd36351): Renamed azure-pipelines.yml to azure-pipelines-server.yml
* 2023-08-08 (e4e8b8b2): Renamed azure-pipelines-1.yml to azure-pipelines-web.yml
* 2023-08-08 (bc49decc): Update azure-pipelines.yml for Azure Pipelines
* 2023-08-08 (6665d684): Update azure-pipelines.yml for Azure Pipelines
* 2023-08-08 (39aa9552): Update azure-pipelines.yml for Azure Pipelines
* 2023-08-08 (12e5f8ae): Set up CI with Azure Pipelines
* 2023-08-08 (5cda4407): Update azure-pipelines-1.yml for Azure Pipelines
* 2023-08-08 (280c267a): Update azure-pipelines-1.yml for Azure Pipelines
* 2023-08-08 (99e71496): Update azure-pipelines-1.yml for Azure Pipelines
* 2023-08-08 (2fc30bab): Set up CI with Azure Pipelines
* 2023-08-08 (61453ad9): Update azure-pipelines.yml for Azure Pipelines
* 2023-08-08 (bef4dfa1): Set up CI with Azure Pipelines
* 2023-08-08 (5ba3b004): Merge pull request #31 from xeptagondev/heatmap-development-frontend
* 2023-08-08 (13dd394c): updated package.json for loading react-heatmap-grid from github
* 2023-08-08 (42cec7a1): Merge pull request #30 from xeptagondev/Improve/regionStat
* 2023-08-08 (236115bf): Reverse the table order
* 2023-08-08 (9a74bf54): Merge pull request #29 from xeptagondev/heatmap-development-frontend
* 2023-08-08 (c80ed14c): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into heatmap-development-frontend
* 2023-08-08 (e431c0f8): refactored code and updated font family
* 2023-08-08 (b8e48df0): Change wording "Grand Total" to "Global"
* 2023-08-08 (6144ff5f): Merge pull request #27 from xeptagondev/Improve/regionStat
* 2023-08-08 (8cd94909): Merge branch 'develop' into Improve/regionStat
* 2023-08-08 (644563ab): Reverse accountability page chart order
* 2023-08-08 (8f154473): Merge pull request #26 from xeptagondev/Improve/regionStat
* 2023-08-08 (55e400a7): deleted
* 2023-08-08 (7716718f): basic header with color interpolation done
* 2023-08-08 (e84860e9): Merge branch 'develop' into Improve/regionStat
* 2023-08-08 (baac5051): Revert testing value
* 2023-08-08 (0e342217): Test github action failiure
* 2023-08-08 (b5d8d59e): Update github workflow
* 2023-08-08 (d72a6d33): Resolve lint issues
* 2023-08-08 (2bba3f37): Merge pull request #25 from xeptagondev/Improve/regionStat
* 2023-08-08 (94657680): Uncommented
* 2023-08-08 (705e2856): Resolve lint isuues
* 2023-08-08 (028bd8a3): Add grand total to the regionStatFunc
* 2023-08-08 (63324a7f): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into heatmap-development-frontend
* 2023-08-08 (2bbdc9b3): added basic heatmap
* 2023-08-07 (35d7cda0): Merge pull request #24 from xeptagondev/side-navigation-and-footer
* 2023-08-07 (b6fb83db): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into side-navigation-and-footer
* 2023-08-07 (4c12ad63): fixed issues in sidenavbar and footer
* 2023-08-07 (10e23a7f): Merge pull request #23 from xeptagondev/side-navigation-and-footer
* 2023-08-07 (0e4d82b3): updated body height
* 2023-08-07 (851924a9): updated
* 2023-08-07 (7b94b17f): Update backend url
* 2023-08-07 (bb8f7787): updated
* 2023-08-07 (eac72314): Merge pull request #22 from xeptagondev/side-navigation-and-footer
* 2023-08-07 (9d5a9ef2): added react-heatmap-grid customized library
* 2023-08-07 (f8a2005e): fixed layout alignment issue that arose from changes in side navbar
* 2023-08-07 (532a83b2): Merge pull request #21 from xeptagondev/Fix/Accountability
* 2023-08-05 (bb025685): added footer
* 2023-08-04 (684f60de): Update the title format
* 2023-08-04 (e2cae4b6): Improve accountability stats
* 2023-08-04 (5c345aae): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into side-navigation
* 2023-08-04 (6b68d62c): fixed issue in side nav not displaying well when width is increased
* 2023-08-04 (a6e6c04f): fixed issue in home page
* 2023-08-04 (1f0d8570): removed some unnecessary code
* 2023-08-04 (1b0a706d): made nav footer position more dynamic
* 2023-08-04 (ff457a4e): fixed issue in content scrolling interaction
* 2023-08-04 (526d079e): added padding-right to hamburger icon and reduced margin from header
* 2023-08-04 (a480b26d): Merge pull request #20 from xeptagondev/Update/Arquero
* 2023-08-04 (6c3e1b69): Update github workflow and unut tests
* 2023-08-04 (c3164c8e): made the content scrollable
* 2023-08-04 (72742fb0): Merge pull request #19 from xeptagondev/Update/Arquero
* 2023-08-04 (8f20c296): Resolve lint issues
* 2023-08-04 (3bc25d16): added methodology icon and section in navbar
* 2023-08-04 (81099894): Merge pull request #18 from xeptagondev/Update/Arquero
* 2023-08-04 (d7230141): Commit yarn lock
* 2023-08-04 (19a845ea): Merge pull request #16 from xeptagondev/Update/Arquero
* 2023-08-04 (5ea28b07): changed production function app
* 2023-08-04 (d46ec21c): added icon for methodology
* 2023-08-04 (d0b13de8): made the navbar scrollable
* 2023-08-03 (01d8388e): Merged PR 1: Latest
* 2023-08-03 (69471a5d): fixed hover color issue in side navigation
* 2023-08-03 (6d313400): Merge pull request #17 from xeptagondev/fix-issues-in-impact-page
* 2023-08-03 (188d8595): Update github workflow
* 2023-08-03 (424e0537): Add heatmap stat
* 2023-08-03 (4befd473): made the map unrotatable
* 2023-08-03 (9bee0978): Merge branch 'develop' into Update/Arquero
* 2023-08-03 (d5ce85c3): Update danfojs to arquero
* 2023-08-02 (49a71fa3): made map undraggable and added minZoom so that it wont look like padding is increasing on top when zooming out
* 2023-08-02 (b91a7d78): fixed the issue in headers not showing fully in All IRRF Output table and Struggling indicator tables in IRRF
* 2023-08-02 (efe7d318): only ticks that are multiples of 20 are showing in the y axis of signature solutions
* 2023-08-02 (5d09489e): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into fix-issues-in-impact-page
* 2023-08-02 (e55228ad): added % mark to y axis ticks
* 2023-08-02 (064fa97a): added x-axis and y-axis labels in strings module
* 2023-08-02 (aa4bcad0): added axis and styling for the axis
* 2023-08-02 (a8e06060): fixed typo (interaction -> interactions)
* 2023-08-02 (dbbba5b1): added padding to bottom of the content
* 2023-08-02 (15c0b477): Merge pull request #14 from xeptagondev/fix-typo
* 2023-08-02 (182b9301): Fix color label
* 2023-08-02 (77f6961e): Fix color change 2023-08-02 (4aa42ee6): changed string constant NotOnTrack -> OffTrack 2023-08-02 (e4fd3602): changed Not On Track -> Off Track 2023-08-02 (06fcf9aa): fixed typo

### July

* 2023-07-31 (edc82ad7): Merge pull request #13 from xeptagondev/update-charts
* 2023-07-31 (954b1cb0): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into update-charts
* 2023-07-31 (25ccca74): updated the country audit table graph
* 2023-07-31 (dfdfe714): Add style changes to legend
* 2023-07-30 (1ec3f82b): add legend to IRRF
* 2023-07-31 (ce5d44a6): updated and removed duplicated components
* 2023-07-31 (015be05c): changed title
* 2023-07-31 (31cad01d): fixed issue in side navbar less space
* 2023-07-31 (ae7d66e6): fixed merge issues
* 2023-07-30 (0f9b5d9f): legend color update
* 2023-07-30 (684e3ab5): Add remainig impact changes
* 2023-07-30 (63750757): add Impact page
* 2023-07-30 (3038917d): change impact region response format
* 2023-07-30 (02e7228a): add new stat type
* 2023-07-29 (08183311): Fix impact func issue
* 2023-07-29 (aad2c189): Fix Impact BE changes
* 2023-07-29 (b7efd8ab): getting data from backend for IRRF page
* 2023-07-29 (35903a4f): Fix remaining UI changes
* 2023-07-29 (a18fd6ef): Fix UI issues
* 2023-07-29 (64bbf472): Add prop tile
* 2023-07-28 (0c91abe7): Add nav links
* 2023-07-28 (d6bf0121): Merge pull request #11 from xeptagondev/ImpactPage
* 2023-07-28 (5926ac4b): Refactor to resolve lint issues
* 2023-07-28 (c54a6eba): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-28 (554c372f): table for map done
* 2023-07-28 (2bd986ed): Merge pull request #10 from xeptagondev/ImpactPage
* 2023-07-28 (6eacc7b7): Add impact page endpoint
* 2023-07-28 (a5f34d47): Fix remaning issue in accountability
* 2023-07-28 (b481940d): Comment Navbar unwanted links
* 2023-07-28 (1b17cb86): created struggling indicators and irrf targets map
* 2023-07-28 (8d47e64d): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-28 (9308e298): added All IRRF output table
* 2023-07-28 (f06a29b8): changed the structure of DummyFocusData.json to avoid loaders not available issue
* 2023-07-28 (4a3d4a3b): Fix lint issues
* 2023-07-28 (fa53a52e): add static card
* 2023-07-28 (bcd178f4): resolved merge conflicts
* 2023-07-28 (edc7aee6): updated and restructured components
* 2023-07-28 (adaf072c): Add accountability widgets
* 2023-07-28 (6ccdf527): add color
* 2023-07-28 (01477adf): add prec
* 2023-07-28 (25063050): revert ts remove
* 2023-07-28 (25b1cbdc): remove tf
* 2023-07-27 (081f4e9c): add total stats
* 2023-07-27 (4c4bbe99): add BE conectivity
* 2023-07-27 (0b0e5a07): global install
* 2023-07-27 (7cadbcb6): Fix deployment issue
* 2023-07-27 (b1bb323f): fix trigger deploy issue
* 2023-07-27 (699647a0): resolved merge conflicts
* 2023-07-27 (89e5b124): updated and resturctured and created dummy files for data and created basic component for IRRF page
* 2023-07-27 (a5fb4150): created hardcoded text cards and created correlations between signature solution across regions
* 2023-07-27 (27633931): add dep
* 2023-07-27 (ef62e429): Deploy audit stats endpoint
* 2023-07-27 (fc693e37): Add blob read
* 2023-07-27 (10342dbe): add accountability page
* 2023-07-27 (1ed8c9c1): Merge pull request #9 from xeptagondev/Feature/handler
* 2023-07-27 (cb1822de): Add storage-blob, dotenv, exceljs packages
* 2023-07-27 (ffaaeaf1): Add blob reading
* 2023-07-27 (1b6153a7): Add routing issues
* 2023-07-27 (5f6c9898): Sitebar update
* 2023-07-27 (e1bdf2dd): updated stat cards for update styles dynamically
* 2023-07-27 (17b6e59a): Remove node version print
* 2023-07-27 (77a66e1d): removed the logo and navbartitle info
* 2023-07-27 (a4c572be): updated
* 2023-07-27 (ec57ceb5): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-27 (cb25076e): fixed issue in mapboxgl-canvas css class
* 2023-07-27 (1b1473ef): updated the stat card component for better maintainability
* 2023-07-27 (411f500a): Change node version
* 2023-07-27 (afeaef7e): remove node version
* 2023-07-27 (c1724b6f): Fix node version
* 2023-07-27 (9db580e4): change the build command
* 2023-07-27 (6e27535b): change node version
* 2023-07-27 (a7076bcf): Add publish CICD
* 2023-07-27 (0dd3fbff): Fix script issues
* 2023-07-27 (f3a16b64): Fix CICD
* 2023-07-26 (c5f44c65): Fix CICD issue
* 2023-07-26 (cebd3c4e): Fix mapper generic interface
* 2023-07-21 (09d672e6): Remove hash on web part file name
* 2023-07-20 (1bca1566): update lint profile
* 2023-07-26 (f4cc0b1b): Merge pull request #8 from xeptagondev/server-v2
* 2023-07-26 (cfa35ea7): update dep
* 2023-07-26 (1bf052c9): update structure
* 2023-07-26 (a28dea67): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-26 (896853e1): changed mooshots to sp mooshots and restructured the code
* 2023-07-26 (cfe46ee1): restructured the bookmark section and made the map component more responsive
* 2023-07-26 (7d030287): Merge pull request #7 from xeptagondev/server-v2
* 2023-07-26 (d509af66): Fix lint issues
* 2023-07-26 (b982df49): Merge pull request #6 from xeptagondev/server-v2
* 2023-07-26 (bc449143): Add folder structure
* 2023-07-26 (dcf8686a): Merge pull request #5 from xeptagondev/server-v2
* 2023-07-26 (e6f7a39e): add working directory to CICD
* 2023-07-26 (bae82b9e): add CICD
* 2023-07-26 (9bdeb16f): add initial refactored code
* 2023-07-26 (73225621): added bureaus sections and fixed some issues in navbar
* 2023-07-26 (520cf5e7): added declarations/support for .svg file to be imported using import statement
* 2023-07-26 (af71f2ef): Update connection string
* 2023-07-26 (445f40a7): Add basic structure
* 2023-07-25 (5b3fa11d): removed unnecessary comments
* 2023-07-25 (94dfbcc1): removed unnecessary comments
* 2023-07-25 (e65abe3c): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-25 (b5eea367): table 1 in integrated financial dashboard is done
* 2023-07-25 (72ae9bf1): added @fluentui/example-data for types for creating interfaces for tables
* 2023-07-25 (7e35b956): check az login
* 2023-07-25 (366b49a7): Add az login
* 2023-07-25 (4aad97f8): run without azure buildin function
* 2023-07-25 (a6ade15f): add az checker
* 2023-07-25 (2ff30bda): Use bash for all the steps
* 2023-07-25 (c4debaa4): add bash terminal to defaults
* 2023-07-25 (55906d2d): Run sls deploy in bash
* 2023-07-25 (b07af811): Add a common shell
* 2023-07-25 (22b64bde): Fix step issue
* 2023-07-25 (7f4097af): Revert changes to entrypoint
* 2023-07-25 (b5045292): change terminal for az account show
* 2023-07-25 (9ce092f8): Change the command line for steps
* 2023-07-25 (97b9072a): remove entrypoint from sls-deploy.yml
* 2023-07-25 (5c574190): remove the entrypoint
* 2023-07-25 (8dc3db77): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-25 (20d27756): Change the deploy method
* 2023-07-25 (376b5a4d): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-25 (d7db1444): converted px to rem
* 2023-07-25 (6f005eb4): Add az status command
* 2023-07-25 (79099b5b): Fix indentation
* 2023-07-25 (331a3bc6): Use serverless plugins
* 2023-07-25 (8d8b7812): Add a ls command to serveless.yml
* 2023-07-25 (6089afb8): made statcards section more responsive with screen width
* 2023-07-25 (8f2c6034): Change the server
* 2023-07-25 (9fddd666): Add the common working directory
* 2023-07-25 (422d6681): Remove worling directory from serverless deploy
* 2023-07-25 (edde7782): Fix working directory
* 2023-07-25 (1a1a707c): Add working directory inside the job
* 2023-07-25 (dd98da2a): Fix compile issue
* 2023-07-25 (364a2609): Add working directory in serveless.yml
* 2023-07-25 (0b8cfa76): Change npm ci to npm install
* 2023-07-25 (3351475a): Change serveless yml to fix the directory
* 2023-07-25 (35fb38e8): Update seveless.yml
* 2023-07-25 (6033a6ed): Change serveless version in serveless.yml
* 2023-07-25 (58408ba3): added for enabling environment variables
* 2023-07-25 (cbd14402): updated map styles
* 2023-07-25 (de244870): initMap.js
* 2023-07-25 (9b4fbee2): Update serveless.yml jobs
* 2023-07-25 (1b320ecb): Merge pull request #4 from xeptagondev/PERF-1/6
* 2023-07-25 (11f73e7e): Update serveless.yml
* 2023-07-25 (a3da6a72): Merge branch 'main' into PERF-1/6
* 2023-07-25 (d8cba408): Update serveless.yml
* 2023-07-25 (6312ce3b): Update workflow for sls deploy
* 2023-07-24 (e4e41a50): updated table column widths of integrated financial dashboard
* 2023-07-24 (9fbf64b0): aligned the follow up icon
* 2023-07-24 (feda320b): fixed spacing issues and converted px to rem
* 2023-07-24 (6b8b5442): created a function to convert px to rem
* 2023-07-24 (e23afb39): fixed some spacing issues
* 2023-07-24 (c9a7503b): changed the color of Highlight section
* 2023-07-24 (d217191e): added basic table for integrated dashboard
* 2023-07-24 (64f9a20c): updated
* 2023-07-24 (31075336): updated to add map
* 2023-07-24 (fe4a8c4b): created DummyGraphData.json
* 2023-07-24 (134cac90): added mapboxgl
* 2023-07-21 (bc496a35): Merge pull request #3 from xeptagondev/develop
* 2023-07-21 (11d19d32): Merge pull request #2 from xeptagondev/githubActions
* 2023-07-21 (86e4120e): Add github workflow
* 2023-07-20 (be372c31): Fix lint issues
* 2023-07-20 (a57f777d): fixed side nav link alignment
* 2023-07-20 (dcf192e2): removed unnecessary div tag
* 2023-07-20 (beeb62bf): margin adding to content dynamically
* 2023-07-20 (67184747): fixed background white issues
* 2023-07-20 (e99246ba): fixed alignment in links
* 2023-07-20 (8d06ba99): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-20 (200b720f): updated
* 2023-07-20 (d2202382): updated
* 2023-07-20 (9142186d): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-20 (07d7c5fb): Add blob triger function
* 2023-07-20 (db792876): updated
* 2023-07-20 (5f11aad8): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-20 (7d485669): added margin-right for SideNavbar
* 2023-07-20 (a22663f1): Update price plan
* 2023-07-20 (033b58d1): updated paddings
* 2023-07-20 (be1c4b57): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-20 (d0a7a01b): made the links in side navbar align
* 2023-07-20 (7815d9d2): Update deployment scripts
* 2023-07-20 (b67235db): fixed scorebade line-height and styling
* 2023-07-20 (7ce706c6): fixed positioning in header and navicon in SideNavbar
* 2023-07-20 (e7e8bd5e): Merge branch 'develop' of https://github.com/xeptagondev/undp-performance-app into develop
* 2023-07-20 (04eec882): fixed positioning issues in sidenavbar and header
* 2023-07-20 (a42c4949): added react-router layout
* 2023-07-20 (690322ad): removed unnecessary console.logs
* 2023-07-20 (c61bec04): removed legends in bar charts
* 2023-07-20 (58894096): add server and azure deployment
* 2023-07-20 (ba578a52): moved some strings to en-us.js and added comments in HomePage.tsx for better readability
* 2023-07-20 (4ab29c69): updated
* 2023-07-19 (3f63ee46): resturured
* 2023-07-19 (ba342619): added basic graphs
* 2023-07-19 (5efafbe2): updated and fixed merge issues
* 2023-07-19 (39649a45): updated image paths
* 2023-07-19 (a9e5bc9c): added follow-up.svg and fixed some styling issues
* 2023-07-19 (37e7bc29): Add table graph widget
* 2023-07-19 (dae338b4): updated
* 2023-07-19 (e2d60930): updated bg color
* 2023-07-19 (35d550d7): basic focus card done
* 2023-07-19 (ced21939): updated
* 2023-07-19 (6bfa2462): created DummyFocusCardData.json
* 2023-07-18 (c2b1c44c): updated
* 2023-07-18 (a4011299): updated
* 2023-07-18 (09337209): fixed warnings
* 2023-07-18 (5a25c198): fixed merge conflicts
* 2023-07-18 (5f2778c0): updated
* 2023-07-18 (4e4a6bcb): updated
* 2023-07-18 (82b6bf4e): moved \*.svg file into assets/images/ and created variable.module.scss
* 2023-07-18 (b66b582c): Merge pull request #1 from xeptagondev/develop
* 2023-07-18 (184cbd96): Improve stlying
* 2023-07-18 (9c1635d2): Fix file name issue
* 2023-07-18 (3920a0b6): Add fluent UI layout and react router
* 2023-07-18 (89fb0b45): updated
* 2023-07-18 (7ad762c3): deleted
* 2023-07-18 (f673e722): updated
* 2023-07-18 (ec291796): renamed dummyData -> dummyStatData
* 2023-07-18 (4fad3238): addes static strings to en-us.js
* 2023-07-18 (1d05b427): updated
* 2023-07-18 (c0a9c406): removed unnecessary console.log
* 2023-07-18 (1e3abc85): fixed more styling, positioning issues
* 2023-07-18 (61e6f2c0): updated classnames
* 2023-07-18 (5736f33e): fixed positioning issues
* 2023-07-18 (047f6795): added a grid layout for stat cards
* 2023-07-18 (12c437d3): added more dummy data
* 2023-07-17 (09f77571): added greeting section
* 2023-07-17 (3b5ae56f): removed unnecessary code for get environment message
* 2023-07-17 (d4764306): fixed width of side navbar
* 2023-07-17 (5026d8aa): updated
* 2023-07-17 (ac19fb6b): created dummyData.json and rendering StatCard dynamically
* 2023-07-17 (36ee0e10): sectioned and made the navbar collapsible
* 2023-07-17 (1cfe9c04): added left-arrow.svg
* 2023-07-17 (d1257168): added title and logo for the navbar and made collapsible
* 2023-07-17 (0f8c944b): added permissions for microsoft graph
* 2023-07-13 (901447eb): updated
* 2023-07-13 (27ecaabb): fixed the sapcing issue between the links and the scores
* 2023-07-13 (bc1d3ef2): updated
* 2023-07-13 (0026a748): updated
* 2023-07-12 (b4d4c65e): added logo
* 2023-07-12 (726adf0b): Static card done
* 2023-07-11 (fc7bc224): updated
* 2023-07-11 (551e01ef): moved Header.tsx and Header.module.scss to Header/
* 2023-07-11 (7db8d64a): added svgs for not on track and on track
* 2023-07-10 (b6f22c16): created basic header
* 2023-07-10 (a2e40d21): updated
* 2023-07-10 (f533cf6b): updated fluentUI from v7 to v8
* 2023-07-07 (a20e3ed0): initial commit
