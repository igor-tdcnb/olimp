# olimp
int n, i, c, m=0, j, p = 0, l = 0,k=0,J=0;
	//l,p mass of case in hand; c max mass for one porter; m mass one  porter 
	cout << "enter n & c" << endl;
	cin >> n >> c;
	int a[10];
	for (i = 0; i < 10; i++) a[i] = 0;
	for (i = 0; i < 10; i++) cout << a[i] << " ";
	cout << "enter masses of case" << endl;
	for (i = 0; i < n; i++)  cin >> a[i];
	
	for (i = 0; i < n; i++) cout << a[i] << " "; cout << endl;
	
	for (i = 0; i < n - 1; i++) for (j = i+1; j < n; j++) if (a[i] > a[j]) { m = a[i]; a[i] = a[j]; a[j] = m; }
	m = 0;
	for (i = 0; i < n; i++) cout << a[i] << " ";
	cout<<endl;
	for (i = 0; i < n - 1; i++)
	{
		
		if (a[i]==0) continue; else
		for (j = i + 1; j < n; j++)
		{
			
			if (m < (a[i] + a[j]) && (a[i] + a[j]) <= c) { m = a[i] + a[j]; J = j; }
			//else if (a[i] <= c)  m = a[i];
			cout << m << "  "<<i<<"   "<< J << "  " << endl;
		}
		if (m>0) k++;
		m = 0; if(a[J]>0) a[i] = 0; a[J] = 0;
		for (int q = 0; q < n; q++) cout << a[q] << " "; cout << "   " << k;
		cout << endl;
	}
	for (int q = 0; q < n; q++) if (a[q] > 0 && a[q] <= c) k++;
	cout<<endl<< k << endl;
