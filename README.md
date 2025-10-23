# Voice4u
speechify-clone-open-source 

## Code Branches that one can work on

Our Git workflow uses a **protected branch model** to ensure stability and controlled integration. Below is the detailed workflow:

                   ┌───────────────────────────┐
                   │          main             │
                   │  (protected: prod-ready)  │
                   │  ✅ Only merges allowed    │
                   └─────────────┬────────────┘
                                 ▲
                     Merge PRs   │
                                 │
                   ┌─────────────┴─────────────┐
                   │        release/<version>  │
                   │  (pre-production branch) │
                   │  ✅ Merges to main & dev  │
                   └─────────────┬────────────┘
                                 ▲
                     Merge PRs   │
                                 │
                   ┌─────────────┴─────────────┐
                   │        develop            │
                   │ (protected: next release) │
                   │  ✅ Only PRs from features │
                   └─────────────┬────────────┘
                                 ▲
           Merge PRs             │
                                 │
      ┌───────────────────────┐         ┌─────┴───────────────────┐
      │ feature/<feature>     │         │ contrib/<user>/<feature>│
      │ (new features)        │         │ (open-source PRs)       │
      │ ✅ Push, then PR      │         │ ✅ PR to develop/feature│
      └─────────────┬─────────┘         └─────────────────────────┘


*******************************************************************************

	                  ┌───────────────────────┐
	                  │ hotfix/<issue>        │
	                  │ (urgent fixes)        │
	                  │ ✅ PR or merge to main│
	                  └───────────────────────┘
	                              │
	                              │
	                              ▼
		               ┌───────────────────────────┐
		               │          main             │
		               │  (protected: prod-ready)  │
		               │  ✅ Only merges allowed   │
		               └─────────────v─────────────┘



                      
**Branch rules summary:**
- `main`: Protected, only merges from `release` or `hotfix`.  
- `develop`: Protected, merges only from `feature` branches via PRs.  
- `feature/<name>`: Free to push, merge via PR to `develop`.  
- `release/<version>`: Stabilizes code, merges into `main` and `develop`.  
- `hotfix/<issue>`: Urgent fixes, merge to `main` and optionally `develop`.  
- `contrib/<username>/<feature>`: External contributions via PRs to `develop` or feature branches.
