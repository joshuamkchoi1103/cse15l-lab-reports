**Part 1**<br>
Bug: reverseInPlace() in ArrayExamples

- 
```
	@Test 
	public void testReverseInPlace1() {
    int[] input1 = {3, 2};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{2, 3}, input1);
	}
```
- 
```
	@Test 
	public void testReverseInPlace2() {
    int[] input1 = {3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3}, input1);
	}
```
  - ![Image](Screenshot20231102172002.png)
  -
BEFORE:
```
      static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
AFTER:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i -1] = temp;
    }
  }
```
This fix addresses the issue because before, in the method it would forget the value of arr[i] and we would be losing track of it. Therefore, a temp variable is necessary to remember that value so that it can be assigned to the other index as a result of reversing the order.


**Part 2**<br>
Command: ```find```<br><br>
1. ```-name```<br>
**Example 1:**<br>
Command: ```find -name "chapter-1.txt"```<br>
Output: ```./technical/911report/chapter-1.txt```<br>
In this example, the command is looking for the chapter-1.txt and it returns the file path. This is helpful because rather than trying to find the file by searching manually this command can speed the process.<br>

**Example 2:**<br>
Command: ```find -name "Alcohol_Problems"```<br>
Output: ```./technical/government/Alcohol_Problems```<br>
In this example, the command is looking for the Alcohol_Problems directory and it returns the directory path. This is helpful because rather than trying to find the directory by searching manually this command can speed the process.<br>

2. ```-maxdepth```<br>
**Example 1:**<br>
Command: ```find technical/ -maxdepth 1```<br>
Output:
```
technical/
technical/911report
technical/biomed
technical/government
technical/plos
```
In this example, the command is finding all the files and directories that is only 1 level deep within the technical directory. This is a useful command when you want to take a look at your file structure at a specific depth/level.<br>

**Example 2:**<br>
Command: ```find technical/government/ -maxdepth 1```<br>
Output: 
```
technical/government/
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm
```
In this example, the command is finding all the files and directories within the technical/government directory that is only 1 depth deep maximum. This is convenient because it allows you to put a limit on the depth of the directory tree.

3. ```-ls```<br>
**Example 1:**<br>
Command: ```find technical/government/Alcohol_Problems/ -ls```<br>
Output:
```
5629499534318828      4 drwxr-xr-x   1 joshu    197609          0 Oct 31 12:10 technical/government/Alcohol_Problems/
6473924464450797     32 -rw-r--r--   1 joshu    197609      32413 Oct 31 12:10 technical/government/Alcohol_Problems/DraftRecom-PDF.txt
7599824371293423     36 -rw-r--r--   1 joshu    197609      36564 Oct 31 12:10 technical/government/Alcohol_Problems/Session2-PDF.txt
6192449487740146     96 -rw-r--r--   1 joshu    197609      95891 Oct 31 12:10 technical/government/Alcohol_Problems/Session3-PDF.txt
6755399441161459     80 -rw-r--r--   1 joshu    197609      81409 Oct 31 12:10 technical/government/Alcohol_Problems/Session4-PDF.txt
```
In this example, it is listing the contents of the path(technical/government/Alcohol_Problems) given in the command and it also searches the subdirectories. This is helpful when you want to see what the directory contains through command.<br>

**Example 2:**<br>
Command: ```find technical/911report/ -ls```<br>
Output: 
```8725724278087991      4 drwxr-xr-x   1 joshu    197609          0 Oct 31 12:10 technical/911report/
9851624184930618    120 -rw-r--r--   1 joshu    197609     119387 Oct 31 12:10 technical/911report/chapter-1.txt
14636698789011795     48 -rw-r--r--   1 joshu    197609      47910 Oct 31 12:10 technical/911report/chapter-10.txt
20547673299935584     72 -rw-r--r--   1 joshu    197609      71968 Oct 31 12:10 technical/911report/chapter-11.txt
 7599824371245409    128 -rw-r--r--   1 joshu    197609     129126 Oct 31 12:10 technical/911report/chapter-12.txt
 7036874417824099     92 -rw-r--r--   1 joshu    197609      90943 Oct 31 12:10 technical/911report/chapter-13.1.txt
13229323905458537    112 -rw-r--r--   1 joshu    197609     111804 Oct 31 12:10 technical/911report/chapter-13.2.txt
 9570149208220015    152 -rw-r--r--   1 joshu    197609     152185 Oct 31 12:10 technical/911report/chapter-13.3.txt
 5348024557560183    264 -rw-r--r--   1 joshu    197609     268853 Oct 31 12:10 technical/911report/chapter-13.4.txt
14918173765722494    288 -rw-r--r--   1 joshu    197609     294230 Oct 31 12:10 technical/911report/chapter-13.5.txt
23643898043752852     80 -rw-r--r--   1 joshu    197609      80751 Oct 31 12:10 technical/911report/chapter-2.txt
15199648742433184    264 -rw-r--r--   1 joshu    197609     267519 Oct 31 12:10 technical/911report/chapter-3.txt
11821949021905317    100 -rw-r--r--   1 joshu    197609     100212 Oct 31 12:10 technical/911report/chapter-5.txt
12384898975326636    148 -rw-r--r--   1 joshu    197609     150961 Oct 31 12:10 technical/911report/chapter-6.txt
22517998136910261    128 -rw-r--r--   1 joshu    197609     129949 Oct 31 12:10 technical/911report/chapter-7.txt
 6473924464402894     84 -rw-r--r--   1 joshu    197609      85871 Oct 31 12:10 technical/911report/chapter-8.txt
 8162774324666853    148 -rw-r--r--   1 joshu    197609     151529 Oct 31 12:10 technical/911report/chapter-9.txt
 6192449487692300     12 -rw-r--r--   1 joshu    197609       9440 Oct 31 12:10 technical/911report/preface.txt
```
In this example, it is listing the contents of the path(technical/911report) given in the command and it also searches the subdirectories. This is helpful when you want to see what the directory contains through command.<br>


4. ```-type```<br>
**Example 1:**<br>
Command: ```$ find technical/government/Media/ -type f```<br>
Output:
```
technical/government/Media/5_Legal_Groups.txt
technical/government/Media/Abuse_penalties.txt
technical/government/Media/Advocate_for_Poor.txt
technical/government/Media/agency_expands.txt
technical/government/Media/Aid_Gets_7_Million.txt
technical/government/Media/All_May_Have_Justice.txt
technical/government/Media/Annual_Fee.txt
technical/government/Media/Anthem_Payout.txt
technical/government/Media/AP_LawSchoolDebts.txt
technical/government/Media/Assuring_Underprivileged.txt
technical/government/Media/Attorney_gives_his_time.txt
technical/government/Media/Avoids_Budget_Cut.txt
technical/government/Media/A_helping_hand.txt
technical/government/Media/A_Perk_of_Age.txt
technical/government/Media/balance_scales_of_justice.txt
technical/government/Media/Barnes_new_job.txt
technical/government/Media/Barnes_pro_bono.txt
technical/government/Media/Barnes_Volunteers.txt
technical/government/Media/Barr_sharpening_ax.txt
technical/government/Media/BergenCountyRecord.txt
technical/government/Media/Bias_on_the_Job.txt
technical/government/Media/Boone_legal_service.txt
technical/government/Media/Bridging_legal_aid_gap.txt
technical/government/Media/BusinessWire.txt
technical/government/Media/BusinessWire2.txt
technical/government/Media/Butler_Co_attorneys.txt
technical/government/Media/Campaign_Pays.txt
technical/government/Media/City_Council_Budget.txt
technical/government/Media/Civil_Matters.txt
technical/government/Media/CommercialAppealMemphis2.txt
technical/government/Media/Commercial_Appeal.txt
technical/government/Media/Coup_Reshapes_Legal_Aid.txt
technical/government/Media/Court_Keeps_Judge_From.txt
technical/government/Media/Crains_New_York_Business.txt
technical/government/Media/defend_yourself.txt
technical/government/Media/Disaster_center.txt
technical/government/Media/Do-it-yourself_divorce.txt
technical/government/Media/Domestic_violence_aid.txt
technical/government/Media/Domestic_Violence_Ruling.txt
technical/government/Media/Donald_Hilliker.txt
technical/government/Media/Entities_Merge.txt
technical/government/Media/Eviction_law.txt
technical/government/Media/families_saved.txt
technical/government/Media/Farm_workers.txt
technical/government/Media/Federal_agency.txt
technical/government/Media/Few_who_need.txt
technical/government/Media/fight_domestic_abuse.txt
technical/government/Media/Fire_Victims_Sue.txt
technical/government/Media/Firm_to_the_Poor_Needs_Help.txt
technical/government/Media/FortWorthStarTelegram.txt
technical/government/Media/Free_Legal_Assistance.txt
technical/government/Media/Free_legal_service.txt
technical/government/Media/Funding_cuts_force.txt
technical/government/Media/Funding_May_Limit.txt
technical/government/Media/Funds_Shortage.txt
technical/government/Media/FY_04_Budget_Outlook.txt
technical/government/Media/Ginny_Kilgore.txt
technical/government/Media/Good_guys_reward.txt
technical/government/Media/grants_fail_to_come.txt
technical/government/Media/Greedy_Generous.txt
technical/government/Media/GreensburgDailyNews.txt
technical/government/Media/Hard_to_Get.txt
technical/government/Media/Helping_Hands.txt
technical/government/Media/Helping_Out.txt
technical/government/Media/help_rent-to-own_tenants.txt
technical/government/Media/Higher_court.txt
technical/government/Media/Higher_Registration_Fees.txt
technical/government/Media/highlight_Senior_Day.txt
technical/government/Media/IOLTA_INTEREST_RATE.txt
technical/government/Media/It_Pays_to_Know.txt
technical/government/Media/Justice_for_all.txt
technical/government/Media/Justice_requests.txt
technical/government/Media/Kiosks_for_court_forms.txt
technical/government/Media/Law-school_grads.txt
technical/government/Media/Lawyer_Web_Survey.txt
technical/government/Media/Law_Award_from_College.txt
technical/government/Media/Law_Schools.txt
technical/government/Media/Legal-aid_chief.txt
technical/government/Media/Legal_Aid_attorney.txt
technical/government/Media/Legal_Aid_campaign.txt
technical/government/Media/Legal_Aid_in_Clay_County.txt
technical/government/Media/Legal_Aid_looks_to_legislators.txt
technical/government/Media/Legal_Aid_Society.txt
technical/government/Media/Legal_hotline.txt
technical/government/Media/Legal_services_for_poor.txt
technical/government/Media/Legal_system_fails_poor.txt
technical/government/Media/less_legal_aid.txt
technical/government/Media/Library_Lawyers.txt
technical/government/Media/Lindsays_legacy.txt
technical/government/Media/Local_Attorneys.txt
technical/government/Media/Lockyer_Warns.txt
technical/government/Media/Low-income_children.txt
technical/government/Media/Major_Changes.txt
technical/government/Media/Making_a_case.txt
technical/government/Media/man_on_national_team.txt
technical/government/Media/Marylands_Legal_Aid.txt
technical/government/Media/New_funding_sources.txt
technical/government/Media/New_Online_Resources.txt
technical/government/Media/NJ_Legal_Services.txt
technical/government/Media/Nonprofit_Buys.txt
technical/government/Media/not_accessible_to_disabled.txt
technical/government/Media/Oregon_Poor.txt
technical/government/Media/Owning_a_Piece.txt
technical/government/Media/Paralegal_Honored.txt
technical/government/Media/Philly_Lawyers.txt
technical/government/Media/Politician_Practices.txt
technical/government/Media/Poor_Lacking_Legal_Aid.txt
technical/government/Media/Poverty_Lawyers.txt
technical/government/Media/predatory_loans.txt
technical/government/Media/Pro-bono_road_show.txt
technical/government/Media/Program_Lodges.txt
technical/government/Media/Providing_Legal_Aid.txt
technical/government/Media/pro_bono_efforts.txt
technical/government/Media/Pro_Bono_Services.txt
technical/government/Media/Raising_the_Bar.txt
technical/government/Media/Rental_rules.txt
technical/government/Media/residents_sue_city.txt
technical/government/Media/Retirement_Has_Its_Appeal.txt
technical/government/Media/RoanokeTimes.txt
technical/government/Media/Rumble_in_the_Bronx.txt
technical/government/Media/Self-Help_Website.txt
technical/government/Media/Service_Agency.txt
technical/government/Media/State_funding.txt
technical/government/Media/Supporting_Legal_Center.txt
technical/government/Media/Survey.txt
technical/government/Media/Targeting_Domestic_Violence.txt
technical/government/Media/Terrorist_Attack.txt
technical/government/Media/Texas_Lawyer.txt
technical/government/Media/Texas_Supreme_Court.txt
technical/government/Media/The_Bend_Bulletin.txt
technical/government/Media/The_Columbian.txt
technical/government/Media/The_State_of_Pro_Bono.txt
technical/government/Media/Too_Crucial_to_Take_Cut.txt
technical/government/Media/Towson_Attorney.txt
technical/government/Media/Understanding.txt
technical/government/Media/Unusual_Woodburn.txt
technical/government/Media/Using_Tech_Tools.txt
technical/government/Media/Valley_Needing_Legal_Services.txt
technical/government/Media/Volunteers_Step_Up.txt
technical/government/Media/water_fees.txt
technical/government/Media/Weak_economy.txt
technical/government/Media/Wilmington_lawyer.txt
technical/government/Media/Wingates_winds.txt
technical/government/Media/Workers_aid_center.txt
technical/government/Media/Working_for_Free.txt
```
In this example, the command is looking for files within the given path(technical/government/media) This is convenient because if there is a directory that contains files and subdirectories than using ```-type``` can speed up the process and efficiency.<br>

**Example 2:**<br>
Command: ```find technical/ -type d```<br>
Output: 
```
technical/
technical/911report
technical/biomed
technical/government
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office
technical/government/Media
technical/government/Post_Rate_Comm
technical/plos
```
In this example, the command is searching for all directories within technical and giving the path for each one. This is efficient because it shows all the directories and subdirectories within the path you provide in the argument.<br>


CITED SOURCES<br>
https://www.redhat.com/sysadmin/linux-find-command
Typed in google: find command-line options
