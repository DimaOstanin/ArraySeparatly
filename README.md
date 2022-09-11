# ArraySeparatly
first odds number then evens numbers sort

	public static void evensAndOddsSeparately(int[] arr) {
		for (int j = 0; j < arr.length - 1; j++) {
			for (int i = 0; i < arr.length - 1 - j; i++) {
				if (arr[i] > arr[i + 1]) {
					int temp;
					temp = arr[i];
					arr[i] = arr[i + 1];
					arr[i + 1] = temp;
				}
			}
		}
		int e = 0, o = 0;
		for (int i = 0; i < arr.length; i++) {
			if (arr[i] % 2 == 0) {
				e++;
			} else
				o++;
		}
		int even[] = new int[e];
		int odds[] = new int[o];

		for (int i = 0, e1 = 0, o1 = 0; i < arr.length; i++) {
			if (arr[i] % 2 == 0) {
				even[e1++] = arr[i];
			} else
				odds[o1++] = arr[i];
		}

		for (int i = 0; i < odds.length; i++) {
			arr[i] = odds[i];
		}

		for (int j = 0; j < even.length; j++) {
			arr[odds.length + j] = even[j];
		}
		for (int x : arr)
			System.out.print("[" + x + "]");
		System.out.println();

	}
