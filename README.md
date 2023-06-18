![PadoGrid](https://github.com/padogrid/padogrid/raw/develop/images/padogrid-3d-16x16.png) [*PadoGrid*](https://github.com/padogrid) | [*Catalogs*](https://github.com/padogrid/catalog-bundles/blob/master/all-catalog.md) | [*Manual*](https://github.com/padogrid/padogrid/wiki) | [*FAQ*](https://github.com/padogrid/padogrid/wiki/faq) | [*Releases*](https://github.com/padogrid/padogrid/releases) | [*Templates*](https://github.com/padogrid/padogrid/wiki/Using-Bundle-Templates) | [*Pods*](https://github.com/padogrid/padogrid/wiki/Understanding-Padogrid-Pods) | [*Kubernetes*](https://github.com/padogrid/padogrid/wiki/Kubernetes) | [*Docker*](https://github.com/padogrid/padogrid/wiki/Docker) | [*Apps*](https://github.com/padogrid/padogrid/wiki/Apps) | [*Quick Start*](https://github.com/padogrid/padogrid/wiki/Quick-Start)

---

# Generic (none) Bundle Template

This bundle serves as a template for creating a new generic onlne bundle.

## Installing Bundle

```bash
install_bundle -download bundle-none-template
```

## Use Case

If you are creating a new generic online bundle, then you can use this template to create your bundle repo. It includes all the required files with marked annotations for you to quickly start developing a new online bundle. Please follow the steps shown below.

A generic bundle does not emphasize products and may require zero or more products. PadoGrid uses the term *none* for such bundles. Some of the examples are listed below.

- Bundles that include only Kubernetes and/or Docker solutions.
- Bundles that require two or more products and none of them can be labeled as the primary product.
- Bundles that require the user to manually install products. For example, a tutorial or training bundle that intentionally left out product requirements.

## 1. Create Repo

Select **Use this template** button in the upper right coner to create your repo. Make sure to follow the bundle naming conventions described in the following link.

## 2. Checkout Repo in Workspace

```bash
# PadoGrid 0.9.7+
install_bundle -checkout <bundle-repo-name>

# PadoGrid 0.9.6 and older
install_bundle -download -workspace <bundle-repo-name>

# Switch into the checked out bundle workspace
switch_workspace <bundle-repo-name>
```

## 3. Update Files

Update the files came with the template repo.

- `pom.xml`
- `assembly-descriptor.xml`
- `.gitignore`
- `README_HEADER.md` (Optional)
- `README.md` (This file)
- `README.TEMPLATE` (Remove it when done. See instructions below.)
- `required_products.txt`

### 3.1. pom.xml

The `pom.xml` file contains instructions annocated with **@template**. Search **@template** and add your bundle specifics there.

### 3.2 assembly-descriptor.xml

This file creates a tarball that will be deployed when the user executes the `install_bundle -download` command. Search **@template** and add your bundle specifics there.

### 3.3 .gitignore

The `.gitignore` file lists workspace specific files to be excluded from getting checked in. Edit `.gitignore` and add new exludes or remove existing excludes.

```bash
vi .gitignore
```

Make sure to comment out your workspace directories (components) so that they can be included by `git`.

```console
...
# PadoGrid workspace directories
apps
clusters
docker
k8s
pods
...
```

## 3.4. README_HEADER.md

Enter a short description of your bundle in the `README_HEADER.md` file. This file content is displayed when you execute the `show_bundle -header` command. **Note that this file is optional.** If it does not exist, then the first paragraph of the `README.md` file is used instead.

## 3.5. READEME.md (this file)

Replace `README.md` with the README_TEMPLATE.md file. Make sure to remove `README_TEMPLATE.md` after you have replaced `READEME.md` with it.

```bash
cp README_TEMPLATE.md README.md
git rm README_TEMPLATE.md
```

Update the `READEME.md` file by following the instructions in that file.

## 3.6. required_products.txt

The `required_products.txt` file must include a list of required products and their versions. Its format is described in the following link.

[Relaxed Bundle Naming Conventions](https://github.com/padogrid/padogrid/wiki/User-Bundle-Repos#relaxed-conventions)

## 4. Develop and Test Bundle

You can freely make changes and test the bundle in the workspace. When you are ready to check in, you simply commit the changes using the `git commit` command. For new files, you will need to select only the ones that you want to check in using the `git status -u` and `git diff` commands. For those files that you do not want to check in, you can list them in the `.gitignore` file so that they do not get checked in accidentally.

---

![PadoGrid](https://github.com/padogrid/padogrid/raw/develop/images/padogrid-3d-16x16.png) [*PadoGrid*](https://github.com/padogrid) | [*Catalogs*](https://github.com/padogrid/catalog-bundles/blob/master/all-catalog.md) | [*Manual*](https://github.com/padogrid/padogrid/wiki) | [*FAQ*](https://github.com/padogrid/padogrid/wiki/faq) | [*Releases*](https://github.com/padogrid/padogrid/releases) | [*Templates*](https://github.com/padogrid/padogrid/wiki/Using-Bundle-Templates) | [*Pods*](https://github.com/padogrid/padogrid/wiki/Understanding-Padogrid-Pods) | [*Kubernetes*](https://github.com/padogrid/padogrid/wiki/Kubernetes) | [*Docker*](https://github.com/padogrid/padogrid/wiki/Docker) | [*Apps*](https://github.com/padogrid/padogrid/wiki/Apps) | [*Quick Start*](https://github.com/padogrid/padogrid/wiki/Quick-Start)
